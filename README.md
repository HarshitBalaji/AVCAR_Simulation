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
👉 [Demo Video](./avcar_demo_video.mp4)  

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
The **Autonomous Voice Controlled Arm Robot (A.V.C.A.R.)** is designed as a modular ROS2 system that integrates **voice recognition, object perception, task planning, and motion execution** in a unified simulation pipeline.  

---

### 🔹 High-Level Overview
<p align="center">
  <img src="docs/system-overview.png" alt="System Overview" width="700"/>
  <br/>
  <em>Fig. 1 – High-level overview of A.V.C.A.R. showing the four main modules.</em>
</p>

- **Voice Control Module**: Captures speech and converts it into text (Speechmatics API), then parses it into PDDL goals.  
- **Perception Module**: Detects and localizes objects using YOLOv8; publishes detections as ROS2 messages.  
- **Task Planning Module**: PlanSys2 generates symbolic action sequences (pick, place, move) and replans if needed.  
- **Motion Planning & Execution Module**: MoveIt2 generates collision-free trajectories and executes them in Gazebo.  

---

### 🔹 ROS2 Node Architecture
<p align="center">
  <img src="docs/node-architecture.png" alt="ROS2 Node Architecture" width="700"/>
  <br/>
  <em>Fig. 2 – ROS2 nodes and communication between modules.</em>
</p>

- `voice_node`: Captures and transcribes audio input.  
- `nlp_parser`: Converts text into structured PDDL goals.  
- `yolo_node`: Publishes `/detected_objects` with bounding boxes and labels.  
- `plansys2`: Consumes environment facts + goals and generates task plans.  
- `moveit2`: Executes motion trajectories for the robotic arm.  
- `gazebo`: Provides the simulation environment and feedback.  

---

### 🔹 Data Flow
<p align="center">
  <img src="docs/data-flow.png" alt="Data Flow" width="700"/>
  <br/>
  <em>Fig. 3 – Data flow from user voice command to robotic arm execution in Gazebo.</em>
</p>

1. User gives a **voice command**.  
2. **Voice Control Module** → converts audio to text → generates PDDL goal.  
3. **Task Planning Module** → PlanSys2 generates symbolic action plan.  
4. **Perception Module** → YOLOv8 provides detected objects to the planner.  
5. **Motion Planning & Execution Module** → MoveIt2 generates trajectories.  
6. **Gazebo & RViz2** → simulate and visualize execution.  

---

📌 **Scalability:** This modular design allows easy extension — e.g., swapping the simulated camera with a real one, expanding the action set in the planner, or deploying the same control pipeline to a physical robotic arm.

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
