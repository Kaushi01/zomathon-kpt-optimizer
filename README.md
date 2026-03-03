# KPT Signal Optimizer
Signal-First Kitchen Prep Time Optimization System

## Overview

This project proposes a scalable signal-correction architecture to improve Kitchen Prep Time (KPT) prediction accuracy in large-scale food delivery systems.

Accurate KPT prediction is critical for:
- Reliable customer ETAs
- Efficient rider assignment
- Reduced rider idle time
- Lower order cancellations

Even small prediction errors at scale can lead to significant operational inefficiencies.

---

## Problem Context

Kitchen Prep Time models often rely on manually marked "Food Ready" signals. However, these signals may not accurately reflect true preparation completion due to:

- Human marking inconsistencies
- Rider-influenced marking behavior
- Hidden kitchen load from non-platform orders
- Lack of granular workflow visibility

This introduces label noise and reduces prediction reliability.

---

## Our Approach: Signal-First Architecture

Instead of modifying the prediction model directly, we focus on improving the quality of input signals.

### 1️⃣ GPS-Based True Ready Time Detection
- Rider geofence entry detection
- Wait-time bias identification
- Pickup timestamp validation
- Retrospective label correction for retraining

### 2️⃣ 4-Stage Workflow Redesign
Replace single "Ready" button with:

1. Order Started
2. Cooking Completed
3. Order Packed
4. Ready for Pickup

This introduces structured signal checkpoints and reduces ambiguity.

### 3️⃣ Restaurant Live Rush Score (RLRS)
A dynamic kitchen load estimator based on:
- Order concurrency
- Time-of-day patterns
- Historical throughput rates

---

## System Architecture

5-Layer Signal-to-Prediction Pipeline:

1. Signal Capture Layer
2. Validation & Bias Detection Layer
3. Feature Engineering Layer
4. Model Retraining Layer
5. ETA Prediction Service

---

## Expected Impact

- Reduction in KPT Mean Absolute Error (targeted ~25%)
- Lower rider wait time
- Improved ETA reliability
- Reduced operational cost

---

## Scalability Considerations

- No additional hardware required
- Backend-only signal correction
- Designed for deployment across 300K+ restaurant partners
- Works for both small and high-volume kitchens

---

## Repository Structure
