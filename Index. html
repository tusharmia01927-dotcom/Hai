<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friend Chat App</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #e5ddd5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .chat-container {
            width: 100%;
            max-width: 420px;
            height: 85vh;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        /* Header */
        .chat-header {
            background-color: #075e54;
            color: white;
            padding: 15px 20px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .avatar {
            width: 42px;
            height: 42px;
            background-color: #25d366;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            font-size: 18px;
            color: #075e54;
        }

        .header-info h3 {
            font-size: 16px;
            font-weight: 600;
        }

        .header-info p {
            font-size: 12px;
            color: #d1f7e0;
        }

        /* Messages Area */
        .chat-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            background-color: #efeae2;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .message {
            max-width: 75%;
            padding: 10px 14px;
            border-radius: 10px;
            font-size: 14px;
            line-height: 1.4;
            position: relative;
            word-wrap: break-word;
        }

        .message.received {
            background-color: #ffffff;
            align-self: flex-start;
            border-top-left-radius: 2px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
        }

        .message.sent {
            background-color: #d9fdd3;
            align-self: flex-end;
            border-top-right-radius: 2px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
        }

        .sender-name {
            font-size: 11px;
            font-weight: bold;
            color: #075e54;
            margin-bottom: 3px;
            display: block;
        }

        .timestamp {
            font-size: 10px;
            color: #667781;
            display: block;
            text-align: right;
            margin-top: 4px;
        }

        /* Input Area */
        .chat-input-area {
            background-color: #f0f2f5;
            padding: 10px 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        #message-input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 25px;
            outline: none;
            font-size: 14px;
            background-color: #ffffff;
        }

        #send-btn {
            background-color: #075e54;
            color: white;
            border: none;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: background-color 0.2s;
        }

        #send-btn:hover {
            background-color: #128c7e;
        }
    </style>
</head>
<body>

<div class="chat-container">
    <div class="chat-header">
        <div class="avatar">FC</div>
        <div class="header-info">
            <h3>Friends Squad</h3>
            <p>Online • বন্ধুদের আড্ডা</p>
        </div>
    </div>

    <div class="chat-messages" id="chat-messages">
        <div class="message received">
            <span class="sender-name">Rafi</span>
            কিরে দোস্ত, কী খবর? আজকে কি সবাই মিলে খেলবি?
            <span class="timestamp">11:40 AM</span>
        </div>
    </div>

    <div class="chat-input-area">
        <input type="text" id="message-input" placeholder="মেসেজ লেখো..." autocomplete="off">
        <button id="send-btn" title="Send">➤</button>
    </div>
</div>

<script>
    const chatMessages = document.getElementById('chat-messages');
    const messageInput = document.getElementById('message-input');
    const sendBtn = document.getElementById('send-btn');

    function getCurrentTime() {
        const now = new Date();
        return now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
    }

    function appendMessage(text, type, sender = '') {
        const msgDiv = document.createElement('div');
        msgDiv.classList.add('message', type);

        if (type === 'received' && sender) {
            const nameSpan = document.createElement('span');
            nameSpan.classList.add('sender-name');
            nameSpan.textContent = sender;
            msgDiv.appendChild(nameSpan);
        }

        const textNode = document.createTextNode(text);
        msgDiv.appendChild(textNode);

        const timeSpan = document.createElement('span');
        timeSpan.classList.add('timestamp');
        timeSpan.textContent = getCurrentTime();
        msgDiv.appendChild(timeSpan);

        chatMessages.appendChild(msgDiv);
        chatMessages.scrollTop = chatMessages.scrollHeight;
    }

    function sendMessage() {
        const text = messageInput.value.trim();
        if (text === '') return;

        appendMessage(text, 'sent');
        messageInput.value = '';
        messageInput.focus();

        // Demo auto-reply from a friend
        setTimeout(() => {
            const replies = [
                "ওকে বস, রেডি থাকিস!",
                "হুম, ঠিক আছে। কয়টায় শুরু করবি?",
                "জোশ! আমি এখনই আসছি।"
            ];
            const randomReply = replies[Math.floor(Math.random() * replies.length)];
            appendMessage(randomReply, 'received', 'Rafi');
        }, 1200);
    }

    sendBtn.addEventListener('click', sendMessage);

    messageInput.addEventListener('keypress', function(e) {
        if (e.key === 'Enter') {
            sendMessage();
        }
    });
</script>

</body>
</html>
