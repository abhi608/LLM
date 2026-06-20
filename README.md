# LLM Pretraining Infrastructure Curriculum

## Profile

- Full-time engineer
- Weekdays: 2 hours/day
- Weekends: 3 hours/day
- Total: ~16 hours/week
- Duration: ~20 weeks (~5 months)

## Goal

Become highly proficient in:

- Foundation model training
- Distributed training systems
- GPU optimization
- Parallelism strategies
- Scaling laws
- Training infrastructure

---

# Weekly Learning Framework

Every week:

## Learning (13-14 hrs)

- Lectures
- Reading
- Code walkthroughs
- Implementations

## Design Note (30-60 min)

Write a 1-page design note answering:

1. What problem does this technology solve?
2. Why were previous approaches insufficient?
3. Core architecture/components?
4. Communication pattern?
5. Memory implications?
6. Performance bottlenecks?
7. Production tradeoffs?
8. How would I explain this in a staff-level interview?

## Review (1 hr)

- Flashcards
- Notes cleanup
- Open questions

---

# Phase 0: LLM Foundations for Pretraining Engineers

## Weeks 1-2

Goal:
Build a strong mental model of modern LLMs before diving into CS336 and Megatron-LM.

### Week 1: GPT Internals

Resource:
Let's Build GPT: From Scratch, in Code, Spelled Out
https://www.youtube.com/watch?v=kCc8FmEb1nY

Monday
- Watch first half
- Attention mechanism
- Self-attention intuition

Tuesday
- Finish video
- Transformer architecture

Wednesday
- Rewatch attention sections
- Detailed notes

Thursday
- Implement single-head attention
- Implement multi-head attention

Friday
- Implement transformer block
- Residual connections
- LayerNorm

Saturday
- Train tiny GPT

Sunday
- Design Note #1

Design Note Topic:
How a Transformer Processes Tokens End-to-End

### Week 2: Tokenization + Modern LLM Overview

Resource:
Let's Build the GPT Tokenizer
https://www.youtube.com/watch?v=zduSFxRajkE

Monday
- Watch tokenizer video

Tuesday
- Implement basic BPE tokenizer

Wednesday
- Compare GPT, Llama, and Claude tokenization approaches

Resource:
Deep Dive into LLMs Like ChatGPT
https://www.youtube.com/watch?v=7xTGNNLPyMI

Thursday
- First half
- Pretraining
- Data
- Scaling laws

Friday
- Second half
- RLHF
- Inference
- Reasoning models

Saturday
- Build end-to-end LLM stack diagram

Sunday
- Design Note #2

Design Note Topic:
Modern LLM Training Stack: From Raw Data to ChatGPT

Deliverables Before CS336:

Model Fundamentals
- Why attention works
- Multi-head attention
- RoPE
- RMSNorm

Training
- Next-token prediction
- Scaling laws
- Chinchilla

Systems
- Why attention is memory bound
- FlashAttention motivation
- Tensor parallelism motivation
- FSDP motivation

---

# Phase 1: Stanford CS336

## Weeks 3-8

Resource:
https://cs336.stanford.edu/

Week 3
- Tokenization
- BPE
- Vocabulary construction

Design Note:
Tokenizer Design Tradeoffs

Week 4
- RoPE
- RMSNorm
- SwiGLU
- Transformer architecture

Design Note:
Modern Llama Architecture

Week 5
- FLOPs
- Tensor cores
- GPU memory hierarchy

Design Note:
Performance Model of LLM Training

Week 6
- Triton
- CUDA concepts
- Kernel fusion

Design Note:
Why Kernel Fusion Matters

Week 7
- DDP
- Tensor Parallelism
- Pipeline Parallelism
- Sequence Parallelism

Design Note:
Comparing Distributed Training Strategies

Week 8
- Scaling laws
- Chinchilla
- Dataset quality

Design Note:
Compute-Optimal Training

---

# Phase 2: Megatron-LM

## Weeks 9-11

Resource:
https://github.com/NVIDIA/Megatron-LM

Week 9
- Tensor Parallelism

Design Note:
Tensor Parallelism Internals

Week 10
- Pipeline Parallelism

Design Note:
Pipeline Scheduling and Bubble Reduction

Week 11
- Sequence Parallelism
- Context Parallelism
- MoE

Design Note:
Scaling Beyond Dense Models

---

# Phase 3: DeepSpeed + FSDP

## Weeks 12-13

Resources:
https://github.com/microsoft/DeepSpeed
https://pytorch.org/docs/stable/fsdp.html

Week 12
- ZeRO-1
- ZeRO-2
- ZeRO-3

Design Note:
Evolution of ZeRO

Week 13
- FSDP
- Checkpointing
- Mixed Precision

Design Note:
FSDP vs ZeRO-3

---

# Phase 4: FlashAttention

## Weeks 14-15

Week 14
- IO complexity
- Memory bandwidth

Design Note:
Why Attention Is Memory Bound

Week 15
- FlashAttention-2
- FlashAttention-3

Design Note:
How FlashAttention Achieves Speedups

---

# Phase 5: NCCL and Communication

## Weeks 16-17

Resource:
https://docs.nvidia.com/deeplearning/nccl/

Week 16
- AllReduce
- ReduceScatter
- AllGather

Design Note:
Collective Communication Deep Dive

Week 17
- Ring vs Tree Collectives

Design Note:
Communication Bottlenecks at Scale

---

# Phase 6: Hardware

## Weeks 18-19

Resources:
H100 Whitepaper
Blackwell Architecture

Week 18
- Tensor Cores
- SMs
- Warp Scheduling

Design Note:
Anatomy of an H100

Week 19
- NVLink
- NVSwitch
- HBM

Design Note:
Designing a Frontier Training Cluster

---

# Phase 7: Papers

## Weeks 20-21

Read:

1. Attention Is All You Need
2. Scaling Laws for Neural Language Models
3. Chinchilla
4. PaLM
5. Llama 3 Technical Report
6. Megatron-LM
7. FlashAttention

Week 20 Design Note:
Evolution of Scaling Laws

Week 21 Design Note:
Lessons from Llama 3

---

# Capstone Project

Train a GPT model between 300M and 1B parameters.

Requirements:

- FSDP
- FlashAttention
- Mixed Precision
- Multi-GPU

Track:

- MFU
- GPU Utilization
- Tokens/sec
- Communication Overhead
- Memory Usage

Tools:

- PyTorch Profiler
- Nsight Systems
- Nsight Compute

Final Design Document (5-10 pages):

1. System Architecture
2. Training Configuration
3. Scaling Results
4. Bottlenecks
5. Future Improvements

---

# Interview Preparation Track

Starting Week 7:

Every Sunday:

- One system design explanation
- One paper summary
- One architecture diagram

Example Topics:

- Design Megatron-LM
- Design ZeRO-3
- Design FlashAttention
- Design a 10k GPU Training Cluster
- Design a Trillion-Token Data Pipeline

Goal:

Be able to whiteboard any major pretraining infrastructure component in 15 minutes.
