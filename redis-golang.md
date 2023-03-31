# Redis Docker, Gorm, Golang
**Development by:** 
- Findryankp

## Tutorial
```shell
sudo docker pull redis
docker run --name redis-images -d -p 6379:6379 redis
```

```shell
go get github.com/go-redis/redis
```

```go
package main

import (
	"encoding/json"
	"fmt"

	"github.com/go-redis/redis"
	"gorm.io/driver/mysql"
	"gorm.io/gorm"
)

type User struct {
	gorm.Model
	FullName string `json:"full_name"`
}

func main() {
	// Connect to Redis
	redisClient := redis.NewClient(&redis.Options{
		Addr:     "localhost:6379",
		Password: "",
		DB:       0,
	})

	// Connect to MySQL
	dsn := "findryankp:passwordfindryan@tcp(localhost:3306)/lapakumkm?charset=utf8mb4&parseTime=True&loc=Local"
	db, err := gorm.Open(mysql.Open(dsn), &gorm.Config{})
	if err != nil {
		fmt.Println("Failed to connect to database")
	}

	// Query the database
	var users []User
	db.Find(&users)

	// Convert the results to JSON
	result, err := json.Marshal(users)
	if err != nil {
		fmt.Println("Failed to convert result to JSON")
	}

	// Save the results to Redis
	err = redisClient.Set("users", result, 0).Err()
	if err != nil {
		fmt.Println("Failed to save results to Redis")
	}

	// Retrieve the results from Redis
	val, err := redisClient.Get("users").Result()
	if err != nil {
		fmt.Println("Failed to retrieve results from Redis")
	}

	// Print the results
	fmt.Println(val)
}
```