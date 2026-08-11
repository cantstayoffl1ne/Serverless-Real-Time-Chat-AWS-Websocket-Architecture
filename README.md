# Serverless-Real-Time-Chat-AWS-Websocket-Architecture

Today we built a fully serverless real-time chat application built on AWS, using API Gateway
WebSocket APIs, Lambda, DynamoDB, and SQS. Zero persistent servers, scales to
thousands of concurrent connections.

## Architecture
<img width="1440" height="1200" alt="image" src="https://github.com/user-attachments/assets/6493a551-cc89-4d6f-81b5-ffb8030450b8" />


## What it demonstrates
- **Persistent connections at scale** — API Gateway WebSocket APIs handle
  two-way, stateful connections without a dedicated connection server.
- **Connection state management** — DynamoDB tracks active connection IDs,
  enabling targeted or broadcast message delivery.
- **Event-driven compute** — Lambda functions bound to $connect, $disconnect,
  and custom routes, so compute only runs when something actually happens.
- **Decoupled writes** — SQS absorbs message-persistence load asynchronously,
  so a traffic spike on the chat thread never blocks message delivery.

## Stack
API Gateway (WebSocket) · AWS Lambda · DynamoDB · SQS
