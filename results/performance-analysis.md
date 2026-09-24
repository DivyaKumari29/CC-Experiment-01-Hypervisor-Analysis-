# Performance Analysis Results

## What we tested

- Command used: `sysbench cpu --cpu-max-prime=20000 run`
- This command finds all prime numbers up to 20,000.
- It uses the CPU as fast as possible.
- More "events per second" = faster CPU.

## Type-1 Hypervisor — Proxmox VE

| Parameter | Value |
| --- | --- |
| Hypervisor | Proxmox VE |
| Hypervisor Type | Type-1 |
| Guest OS | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| Total Execution Time | 10.0005 s |
| Total Events | 17,494 |
| Events per Second | 1,749.16 |
| Average Latency | 0.57 ms |

## Type-2 Hypervisor — VMware Workstation

| Parameter | Value |
| --- | --- |
| Hypervisor | VMware Workstation |
| Hypervisor Type | Type-2 |
| Guest OS | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB |
| Disk | 20 GB |
| Total Execution Time | 10.0006 s |
| Total Events | 7,077 |
| Events per Second | 707.43 |
| Average Latency | 1.41 ms |

## Side-by-side comparison

| Parameter | Type-1 (Proxmox VE) | Type-2 (VMware Workstation) |
| --- | --- | --- |
| Total Execution Time | 10.0005 s | 10.0006 s |
| Total Events | 17,494 | 7,077 |
| Events per Second | 1,749.16 | 707.43 |
| Average Latency | 0.57 ms | 1.41 ms |
<img width="2085" height="1497" alt="image" src="https://github.com/user-attachments/assets/eefffb36-5ba0-4409-bade-1aa9f666b351" />

## What each term means

- **Total Execution Time** — how long the test ran. Lower is better.
- **Total Events** — how many calculations were done. Higher is better.
- **Events per Second** — main speed number. Higher = faster.
- **Average Latency** — average time for one calculation. Lower is better.

## Conclusion

- Proxmox VE (Type-1) is faster than VMware Workstation (Type-2).
- Proxmox VE speed: 1,749.16 events/sec.
- VMware speed: 707.43 events/sec.
- Proxmox VE is about **2.5 times faster**.
- Proxmox VE also has lower latency: 0.57 ms vs 1.41 ms.
- Reason: Proxmox VE is Type-1. It runs directly on hardware. No host OS in between.
- VMware Workstation is Type-2. It runs on top of a host OS. This adds extra overhead.
- Extra overhead means slower CPU performance.
- Conclusion: For CPU-heavy tasks, Type-1 hypervisors perform better than Type-2 hypervisors.
