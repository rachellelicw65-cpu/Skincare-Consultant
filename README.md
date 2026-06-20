<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Skincare Consultant</title>
    <style>
        /* Basic reset and full-page styling */
        html, body {
            margin: 0;
            padding: 0;
            height: 100%;
            width: 100%;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            overflow: hidden; /* Prevent scrollbars on the body */
        }
        /* The container for the chat widget */
        #n8n-chat-container {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>

    <!-- This is where the chat widget will be rendered -->
    <div id="n8n-chat-container"></div>

    <!-- Import the @n8n/chat package from a CDN -->
    <script src="https://cdn.jsdelivr.net/npm/@n8n/chat@latest/dist/chat.min.js"></script>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Initialize the n8n chat interface
            n8nChat.init({
                // The HTML element to render the chat in.
                // It must be an existing element on the page.
                target: document.getElementById('n8n-chat-container'),

                // REQUIRED: The webhook URL of your n8n workflow.
                // Replace this placeholder with your actual n8n webhook URL.
                webhookUrl: 'https://ciwali65.app.n8n.cloud/webhook/81b48683-d05c-499b-9bb5-9fbab100ea6c/chat',

                // The initial messages to display when the chat loads.
                initialMessages: [
                    {
                        role: 'assistant',
                        content: "Hello! I'm your personal AI Skincare Consultant. To get started, you can ask me a skincare question or upload a clear, well-lit photo of your face for a personalized analysis and routine recommendation.",
                    },
                ],

                // --- Behavior Customization ---
                behaviorOptions: {
                    // Determines if the chat should process responses as a stream.
                    // Set to false as per the request.
                    enableStreaming: false,

                    // Shows a "..." typing indicator while waiting for the assistant's response.
                    enableTypingIndicator: true,

                    // Allows users to upload files. Essential for the skincare analysis use case.
                    enableFileUpload: true,
                    
                    // Defines the text on the file upload button.
                    fileUploadButtonText: 'Upload Photo',

                    // Defines the text shown in the drag-and-drop area for file uploads.
                    fileUploadDropText: 'Drop your photo here',

                    // Specifies the accepted file types using MIME types. 'image/*' accepts all image formats.
                    fileUploadAccept: 'image/*',
                    
                    // Displays a restart button to clear the conversation.
                    showRestartButton: true,
                },

                // --- Display and Theme Customization ---
                displayOptions: {
                    // The title displayed at the top of the chat window.
                    chatTitle: 'AI Skincare Consultant',
                    
                    // The placeholder text in the message input box.
                    placeholder: 'Describe your skin concerns or upload a photo...',

                    // The color scheme for the chat interface. Options: 'light', 'dark'.
                    colorScheme: 'light',

                    // Main theme color, used for buttons, input focus, and user messages.
                    primaryColor: '#6A9EDA', // A calming, clinical blue

                    // Color of text elements like the title and bot messages.
                    textColor: '#333333',

                    // Background color of the chat bubbles.
                    bubbleBackgroundColor: '#F1F1F1',

                    // Text color inside the chat bubbles.
                    bubbleTextColor: '#333333',

                    // URL for the bot's avatar image.
                    botAvatarUrl: 'https://cdn-icons-png.flaticon.com/512/10009/10009920.png',
                    
                    // URL for the user's avatar image.
                    userAvatarUrl: 'https://cdn-icons-png.flaticon.com/512/1144/1144760.png',

                    // Controls the visibility of the "Powered by n8n" footer. Options: 'n8n', 'none'.
                    poweredBy: 'n8n',

                    // Dimensions of the chat window.
                    width: '100%',
                    height: '100%',
                },
            });
        });
    </script>

</body>
</html>

