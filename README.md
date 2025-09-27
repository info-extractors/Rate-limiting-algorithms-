# Rate Limiting Algorithms: Token Bucket & Leaky Bucket

This repository contains implementations and explanations of two popular **rate-limiting algorithms**: **Token Bucket** and **Leaky Bucket**. These algorithms are widely used in networking, APIs, and distributed systems to control the flow of requests and prevent system overload.

---

## Table of Contents
- [Introduction](#introduction)
- [Algorithms](#algorithms)
  - [Leaky Bucket](#leaky-bucket)
  - [Token Bucket](#token-bucket)
- [Comparison](#comparison)
- [Use Cases](#use-cases)
- [Implementation](#implementation)
- [License](#license)

---

## Introduction

Rate limiting is essential to prevent systems from being overwhelmed by sudden bursts of requests.  
Both **Token Bucket** and **Leaky Bucket** algorithms help enforce request limits but behave differently in handling bursts and controlling flow.

---

## Algorithms

### Leaky Bucket
The **Leaky Bucket** algorithm can be visualized as a bucket with a small hole at the bottom:

- Requests enter the bucket at any rate.
- Requests leave the bucket at a **constant rate**.
- If the bucket overflows, incoming requests are **discarded**.
- Smooths out bursts to maintain a steady flow.

**Key Characteristics:**
- Fixed output rate
- No burst allowance
- Dropped requests when bucket is full

---

### Token Bucket
The **Token Bucket** algorithm uses tokens to control request processing:

- Each request consumes **1 token**.
- Tokens are added to the bucket at a **fixed refill rate**.
- Bucket has a **maximum capacity**, allowing bursts.
- If no tokens are available, the request is **denied or delayed**.

**Key Characteristics:**
- Allows bursts (up to bucket capacity)
- Average rate is controlled by token refill rate
- Flexible and widely used in APIs

---

## Comparison

| Feature           | Leaky Bucket        | Token Bucket          |
|------------------|------------------|--------------------|
| Burst handling     | No (smoothed)      | Yes (allowed)       |
| Output rate        | Constant           | Flexible (up to refill rate) |
| Dropped requests   | When bucket full   | When no tokens      |
| Use case           | Traffic shaping    | API rate limiting with bursts |

---

## Use Cases
- **Leaky Bucket:** Network traffic shaping, smoothing bursts
- **Token Bucket:** API rate limiting, controlling distributed system request rates, handling bursts efficiently

---

## Implementation
This repository contains:
- **Python implementations** of both algorithms
- **Examples and simulations** showing how messages/requests are handled over time
- **Visualization scripts** (optional) to see how bursts are processed

---

## License
This project is l
