#Overview
Traditional TCP congestion control, based on Additive Increase, Multiplicative Decrease (AIMD), struggles to meet the low-latency and high-efficiency demands of modern data centers. This report explores alternative AIMD configurations and introduces AI-driven dynamic parameter tuning to optimize TCP performance in high-speed network environments.

#Key Topics Explored
⚡ Issues with Conventional TCP in Data Centres
1. Inefficiency in handling short messages – Leads to increased tail latency.
2. Stateful per-connection model – Causes scalability bottlenecks.
3. Sender-driven congestion control – Responds too slowly to network conditions.
4. Rigid in-order packet delivery – Prevents optimal load balancing.
🚀 Innovations in TCP for Data Centres
Several next-generation congestion control algorithms are analyzed:

Homa Protocol – Removes in-order packet constraints, reducing latency.
Data Centre TCP (DCTCP) – Uses Explicit Congestion Notification (ECN) for queue management.
AI-Assisted Congestion Control – AI-driven parameter tuning for dynamic adaptability.

#🔬 Experimental Approaches
This project evaluates four congestion control strategies:

##Conventional AIMD (Baseline Model)
Uses fixed α = 1 (additive increase) and β = 0.5 (multiplicative decrease).
Ensures fairness but suffers from slow convergence and inefficiency.

##Adaptive AIMD (AAIMD)
Dynamically adjusts α and β based on congestion levels.
Faster convergence and higher bandwidth utilization compared to AIMD.

##Adaptive Fairness Hybrid Increase Sigmoidal Decrease (AFHISD)
Fairness-aware increase and sigmoid-based decrease to prevent drastic reductions.
Achieves high network utilization but sacrifices fairness.

##AI-Tuned TCP Parameters (GPT-4o Assisted)
Uses AI to dynamically optimize α and β to balance fairness and stability.
Results show that AI performs suboptimally in utilization but adapts dynamically to network conditions.

#Conclusion
No single approach optimally balances fairness, efficiency, and stability.
AFHISD is best for high utilization, but AI-Tuning offers adaptability to changing network conditions.
A hybrid strategy, where AI assists in parameter tuning while deterministic methods execute decisions, could be the most effective solution for real-world deployments.

#Structure
tcp_experiments.ipynb – Contains AIMD, AAIMD, AFHISD, and AI-based TCP simulations.
ai_tuned_tcp.py – Python script for AI-driven TCP parameter tuning.
requirements.txt – Dependencies list for the project.
.env – Stores OpenAI API credentials for AI experiments.
plots/ – Visualization outputs of congestion control simulations
