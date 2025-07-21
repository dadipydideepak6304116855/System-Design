
🧠 What is Backpressure in System Design? (backpressure.md)
🔹 Definition
Backpressure is a flow control mechanism used in systems where data is produced faster than it can be consumed. It prevents system overload by signaling the producer to slow down or pause data transmission when the consumer is overwhelmed.

🔹 Where It's Used
Streaming systems (e.g., Kafka, Flink, Apache Storm)

Message queues (e.g., RabbitMQ, Kafka)

Reactive programming (e.g., RxJava, Project Reactor)

Microservices (via HTTP, messaging, gRPC, etc.)

Operating systems (TCP flow control)

🔹 Why Backpressure is Important
Without backpressure:

Buffers overflow

System crashes or drops messages

High latency due to queue buildup

Poor user experience

With backpressure:

Smooth flow of data

Maintains stability and reliability

Protects downstream services

🔹 Real-World Analogy
Think of a conveyor belt in a factory. If workers at the end can't process items fast enough, the belt will overflow unless the machine feeding it slows down — this slowing down is backpressure.

🔹 How It's Implemented
Pull-based models:

The consumer requests data only when ready.

Example: Reactive Streams (Publisher → Subscriber with request(n))

Acknowledgments (ACKs):

The producer waits for ACK before sending more.

Used in messaging systems like RabbitMQ, Kafka

Buffer limits:

When buffer size is hit, producers are blocked/throttled.

Rate limiting:

Producers are restricted to fixed data rates.

Circuit breakers:

Temporarily reject new requests when the system is overwhelmed.

🔹 Example in Microservices
If Service A calls Service B rapidly but B is slow, then:

Service B's threads/queue may fill up.

It sends backpressure signals (e.g., 429 Too Many Requests, or gRPC backpressure).

Service A can retry later or slow down.

