# OS Jackfruit Project

## Team Members

Pranav V Menon — SRN:PES1UG24AM198
Purvik V Gowda — SRN: PES1UG24AM211

---

## Project Description

This project is based on the Jackfruit operating systems assignment. The goal is to experiment with system workloads and observe how the Linux operating system handles CPU, memory and IO usage.

The repository contains a kernel module for monitoring along with a few workload programs that generate resource pressure on the system. These workloads help demonstrate scheduling behaviour and resource usage.

---

## Files in the Repository

* **engine.c** – user space runtime file
* **monitor.c** – kernel module for monitoring
* **monitor_ioctl.h** – header file used for communication
* **cpu_hog** – program that consumes CPU cycles
* **memory_hog** – program that allocates memory repeatedly
* **io_pulse** – program that generates IO activity
* **Makefile** – used to build the project

---

## Build Instructions

Go to the boilerplate directory:

```
cd boilerplate
```

Compile the project:

```
make
```

---

## Loading the Kernel Module

Insert the monitoring module:

```
sudo insmod monitor.ko
```

Check if it loaded:

```
lsmod | grep monitor
```

---

## Running the Workloads

Memory workload:

```
./memory_hog
```

CPU workload:

```
./cpu_hog
```

IO workload:

```
./io_pulse
```

These programs simulate different types of resource usage on the system.

---

## Scheduling Experiment

To measure the CPU workload runtime we used:

```
time ./cpu_hog
```

Example output:

```
real 0m9.699s
user 0m9.698s
sys  0m0.013s
```

This shows how the system schedules a CPU intensive task.

---

## Viewing Kernel Logs

Kernel messages from the module can be viewed using:

```
sudo dmesg | tail
```

---

## Cleaning Up

Remove the kernel module:

```
sudo rmmod monitor
```

---

## Summary

Through this project we experimented with CPU, memory and IO workloads and observed how the operating system manages resources and scheduling.
