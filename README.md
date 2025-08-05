🦾 3-Joint Robotic Arm Simulation with Inverse Kinematics, Trajectory Spline, and Real-Time Animation

This project simulates a **3-joint robotic arm** with:
- Two **rotational joints**
- One **linear actuator**
- Real-time animation
- User-defined waypoints
- Full **Inverse & Forward Kinematics**
- **Cubic spline trajectory generation**
- Real-time **joint plotting** and **position tracking**

---

## 🔧 Features
- 🧠 Inverse Kinematics for 3D target positioning
- 🦿 Forward Kinematics for pose calculation and plotting
- ✍️ User input for custom XYZ waypoints
- 📈 Real-time simulation of joint movement
- 🧮 Joint trajectory profiles (θ1, θ2, d3) over time
- 🎯 End-effector position printed at every time step
- 🔁 Spline-based motion planning using SciPy
- 📊 Chart comparing actual vs expected path

---

## ▶️ How to Run

1. Install requirements:
```bash
pip install numpy matplotlib scipy
Run the simulation:

python robotic_arm_simulation.py
You'll be prompted to enter custom waypoints, or use default ones.

✨ Sample Output: Real-Time Joint & Position Print

Step 087: t=8.60s | θ1=32.05°, θ2=-35.99°, d3=42.42mm | X=182.43, Y=114.21, Z=83.70
📊 Actual End-Effector Path vs Original Waypoints
This plot compares:

<img width="1006" height="1024" alt="image" src="https://github.com/user-attachments/assets/0b9f0d98-3e5b-4256-9482-2ec8ba1bf0ea" />


🔵 Original waypoints (user input)

🔴 Actual path (generated via forward kinematics at each step)


📈 End-Effector Tracking Accuracy
Final position reached by the robot:

X = 197.20 mm
Y = 134.45 mm
Z = 91.74 mm
Target final waypoint:

X = 220 mm
Y = 150 mm
Z = 110 mm
🔎 Delta: ~22.8 mm (X), ~15.5 mm (Y), ~18.3 mm (Z)

This deviation is expected due to:

Cubic spline smoothing 

Reach limits enforced in IK

Nonlinear geometry of robotic arm

🧠 Why Use a Spline?
Cubic splines make movement smooth and realistic.

s=0: Hits every waypoint exactly, no smoothing

s=1: (default) Smoother trajectory, reduced jerk, more fluid arm behavior

💡 Optional Enhancement – No Spline (Exact Waypoint Hits)
If precision is more important than smoothness, consider bypassing the spline and using raw waypoints:

# Instead of:
x_spline, y_spline, z_spline = generate_spline(waypoints)

# Use:
x_spline, y_spline, z_spline = zip(*waypoints)
This will force the robot to move exactly through each defined point.


🚀 Author
Ali Witwit
Robotics Enthusiast
