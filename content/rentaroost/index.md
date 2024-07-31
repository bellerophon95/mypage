+++
draft = false
title = "Project Rentaroost"
date = 2024-07-31T16:29:49+05:30
+++

Rent-a-Roost is an Airbnb clone that allows users to view listings and book them after payment. The application integrates various cutting-edge technologies to provide a seamless user experience, dynamic pricing, and reliable payment processing.

## Features

1. **Integration with Stripe API**  
   Secure and reliable payment processing upon booking. Real-time payment confirmation.

2. **Dynamic Pricing**  
   Prices are adjusted based on the number of views and successful bookings. Ensures competitive pricing and maximizes revenue.

3. **Push Notifications**  
   Users receive notifications for successful payments, bookings, and price drops. Real-time updates keep users informed and engaged.

## Architecture

1. **GraphQL with Netflix DGS**  
   User-facing API built with GraphQL for efficient and flexible data querying. Utilizes Netflix DGS for rapid development and scalability.

2. **Apache Kafka Saga Pattern**  
   Handles mutation flows, including payments, bookings, and listing creation. Supports WebFlux for write flows to ensure non-blocking, reactive processing.

3. **Unary Synchronous gRPC**  
   Read queries are handled using unary synchronous gRPC. A rudimentary CQRS-like approach separates commands and queries. Plans to optimize read flows using non-blocking stubs in the future.

4. **Push Notifications with Firebase Cloud Messaging**  
   Push notifications implemented using Firebase Cloud Messaging. Basic client developed in NextJS.

5. **Dynamic Pricing Calculations**  
   Uses Apache Flink and Kafka for dynamic pricing. Watermarks account for out-of-order and late arrivals due to computation and bandwidth latencies. Different impacts on price delta for view and booking events.

6. **Redis for Dynamic Pricing Deltas**  
   Dynamic pricing deltas stored in Redis, used in conjunction with a Kafka sink. Redis Hashes with TTLs to remove dynamic pricing impact after expiration. Redis pub/sub triggers push notifications for price drops. Plans to upgrade to Cassandra for writing dynamic pricing deltas and integrate Apache Druid for pricing analytics.

7. **Spring Boot with MongoDB**  
   Primary database is MongoDB, providing document-level transaction guarantees for sensitive payment flows. Spring Boot framework ensures robust and maintainable backend services.

8. **Deployment on Kubernetes**  
   The entire application is containerized and deployed on Kubernetes. Ensures scalability, high availability, and easy management.

## Future Improvements

1. **Cassandra Integration**  
   Upgrade from Redis to Cassandra for better scalability and durability.

2. **Apache Druid Integration**  
   Optimize pricing strategies with advanced analytics.

3. **Non-blocking gRPC**  
   Transition to non-blocking gRPC stubs for improved performance on read queries.

4. **Enhanced User Interface**  
   Further refine the NextJS client for a better user experience.

## Conclusion

Rent-a-Roost showcases the integration of various modern technologies to create a robust, scalable, and user-friendly application. The project demonstrates expertise in system design, architecture, and the use of reactive and non-blocking frameworks to handle high concurrency and ensure reliable operations.

For more details, please visit the [GitHub repository](https://github.com/bellerophon95/rentaroost).
