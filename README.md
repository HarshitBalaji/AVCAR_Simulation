# Autonomous Voice Controlled Arm Robot (A.V.C.A.R)

**Final Year Project – B.E. Computer Science & Engineering (2023–24)**  
BMS Institute of Technology & Management, Bengaluru  
Visvesvaraya Technological University, Belagavi  

---

## 📌 Overview
The **Autonomous Voice Controlled Arm Robot (A.V.C.A.R)** is a simulated assistive robotics project developed using **ROS2 Humble**, **PlanSys2**, **MoveIt2**, **YOLOv8**, and **Speech Recognition APIs**.  

The system enables a simulated robotic arm to:
- Understand **voice commands** from the user.  
- Perform **object detection** and localization using YOLOv8.  
- Generate autonomous **task plans** via PlanSys2 (PDDL-based planner).  
- Execute **pick-and-place motions** using MoveIt2 within Gazebo.  

This work demonstrates the feasibility of combining **AI perception**, **symbolic planning**, and **motion control** in a single ROS2 pipeline for assistive robotics.  

---

## 🎥 Demo
A short video demonstration of the project can be viewed here:  
👉 [Demo Video](<./AVCAR_demo.webm)  

---

## 📖 Documentation
For detailed methodology, architecture, and testing results, please refer to:  
- [📄 Final Year Thesis (PDF)](./Final%20Year%20Thesis.pdf)

---

## 🛠️ Tech Stack
- **ROS2 Humble** – Middleware for robotics applications  
- **PlanSys2** – PDDL-based planning framework for task sequencing  
- **MoveIt2** – Motion planning and execution  
- **Gazebo & RViz2** – Simulation and visualization  
- **YOLOv8 (Lite)** – Object detection  
- **Speechmatics API** – Speech-to-text transcription  
- **Gemini API** – Natural language to PDDL translation  
- **Python (rclpy)** & **C++ (rclcpp)** – ROS2 client libraries  

---

## ⚙️ System Architecture
The system is divided into four core modules:
1. **Voice Control Module** – Transcribes user speech and converts it into PDDL goals.  
2. **Perception Module** – Detects and localizes objects using YOLOv8.  
3. **Task Planning Module** – Uses PlanSys2 to generate and replan task sequences.  
4. **Arm Control & Simulation Module** – Executes pick-and-place actions in Gazebo using MoveIt2.  

---

## 🚀 Features
- Natural language interaction through **voice commands**.  
- Autonomous **task sequencing** with automatic replanning on failures.  
- Integration of **deep learning–based object detection** with symbolic planning.  
- Full simulation in **Gazebo** with a URDF-based robotic arm model.  

---

## 📊 Results
- YOLOv8 trained on a custom dataset (3 object classes) – achieved ~80% detection accuracy.  
- Plansys2 generated task plans averaging **6–7 steps per command**.  
- Successful pick-and-place operations demonstrated in Gazebo.  

---

## 👨‍💻 Team
- [Chaitra Sri Naidu](https://github.com/chytra3)  
- [S Guru Prasad](https://github.com/Guru-Prasad-2002)  
- [Sai Harshit B](https://github.com/HarshitBalaji)  
- [Vigneshwaran P S](https://github.com/Vigneshwaran30)  

Under the guidance of **Dr. Ambika G N**, Assistant Professor, Dept. of CSE, BMSIT&M.

---

## 📌 Ongoing Work
- Full real-time integration of YOLOv8 into ROS2 pipeline.  
- Hardware implementation on a physical robotic arm.  
- Expanded dataset and improved multi-object grasping.  

---
