# home-lab-setup
Documentation of my personal home lab — AI inference, Linux server, virtualization, and NAS.

## Overview

This repository documents the setup, configuration, and decisions behind my home lab. The lab runs local AI inference, a Linux NAS, KVM virtualization, and a multi-GPU workstation — all self-built and self-administered. Everything here was done without formal IT training, driven by curiosity and practical need.

## Machines

Machine 1 — AI Inference Server (Linux)

CPU:  Intel i5
RAM:  120GB DDR4
GPU:  NVIDIA 16GB + AMD 16GB (hybrid acceleration)
OS:   Ubuntu 24.04 LTS
Role: Local LLM inference via llama.cpp (compiled from source)

Machine 2 — Workstation / Dev (Windows 11)

CPU:  AMD Ryzen 9900
RAM:  64GB DDR5
GPU:  NVIDIA 8GB + NVIDIA 6GB
OS:   Windows 11
Role: Primary workstation, development, model testing

Machine 3 — Home Server (Linux, headless)

CPU:  Intel i7 10th Gen
RAM:  47GB
Storage: 2x 8TB HDD (network-accessible, persistent mount)
OS:   Ubuntu Server (SSH only)
Role: NAS + KVM host + Cockpit management
## What's Running

Local AI Inference

Capable of running any of this models:

gemma-4-31B-it-UD-Q4_K_XL.gguf  
LFM2.5-1.2B-Instruct-BF16.gguf                                 
Qwen3.6-35B-A3B-UD-Q4_K_XL.gguf           
Qwopus3.5-9B-v3.BF16.gguf
gpt-oss-20b-UD-Q8_K_XL.gguf     
NVIDIA-Nemotron-3-Nano-Omni-30B-A3B-Reasoning-UD-Q4_K_XL.gguf  
Qwen3-Coder-30B-A3B-Instruct-Q5_K_M.gguf  
Qwopus-GLM-18B-Healed-Q8_0.gguf

via llama.cpp compiled from source with support for both NVIDIA CUDA and AMD ROCm on Machine 1. The goal was to run a capable local model without ongoing API costs while learning systems programming and AI infrastructure.

NAS (Network Attached Storage)

Two 8TB drives configured with persistent mounts on Ubuntu Server, accessible across the home network via Samba. Used for media storage and backup.

KVM Virtualization + Cockpit

KVM running on the same Ubuntu Server machine as the NAS, managed through Cockpit web UI via browser. Used for spinning up isolated Linux environments for testing and learning without risking the host OS.

## Why This Exists

I built this lab to learn Linux systems administration, AI infrastructure, and eventually software development — all in a real environment I control. I am a bilingual (English/Spanish) AV and IT production professional with 13 years of experience in live events and broadcast. This lab is where I bridge that production background with deeper systems knowledge.

## Build session recording

Full build session recorded live — covers persistent UUID-based mounting, XFS formatting, 
Samba configuration for cross-platform access (Windows, macOS, Linux), SELinux hardening, 
firewalld rules, and Cockpit web dashboard setup on Ubuntu Server.

Built and documented using a local LLM (llama.cpp) as the primary reference — no cloud AI, 
no paid subscriptions.

▶ [Watch the full session on YouTube](https://www.youtube.com/watch?v=1VmxnDgfIWE)

## In Progress

- Learning Python as foundation for software development
- Exploring 2D game development (Godot)
- CompTIA Linux+ certification — planned
