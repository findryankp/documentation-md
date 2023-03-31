# Create Bucket - Google Cloud Console
**Development by:** 
- Findryankp

## Tutorial
To get the serviceAccountKey.json file, you'll need to follow these steps:
1. Go to the Firebase Console and select your project.
2. Click on the gear icon in the top-left corner and select "Project Settings."
3. Click on the "Service Accounts" tab.
4. Click on the "Generate New Private Key" button.
5. Save the generated JSON file to a secure location on your computer.
This JSON file contains the private key that you'll need to authenticate your application when making requests to Firebase services, such as sending push notifications using Firebase Cloud Messaging.

Note: Keep this file secure and don't share it with anyone, as it allows access to your Firebase project.

## Example
```go
package main

import (
	"context"
	"fmt"

	firebase "firebase.google.com/go"
	"firebase.google.com/go/messaging"
	"google.golang.org/api/option"
)

func main() {
	ctx := context.Background()
	opt := option.WithCredentialsFile("./firebase.json")
	app, err := firebase.NewApp(ctx, nil, opt)
	if err != nil {
		fmt.Printf("error initializing app: %v\n", err)
		return
	}
	client, err := app.Messaging(ctx)
	if err != nil {
		fmt.Printf("error initializing messaging client: %v\n", err)
		return
	}

	// Define the message to send
	message := &messaging.Message{
		Notification: &messaging.Notification{
			Title: "Hello",
			Body:  "World",
		},
		Topic: "example-topic",
	}

	// Send the message
	response, err := client.Send(ctx, message)
	if err != nil {
		fmt.Printf("error sending message: %v\n", err)
		return
	}
	fmt.Printf("message sent: %v\n", response)
}
```