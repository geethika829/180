# 180
# Function to distribute the total angle equally among the motors
def distribute_angles(total_angle, num_motors):
    if total_angle % num_motors != 0:
        raise ValueError("The total angle should be divisible by the number of motors for equal distribution.")
    
    angle_per_motor = total_angle // num_motors
    return [angle_per_motor] * num_motors

# Define the total angle and the number of motors
total_angle = 180
num_motors = 3

# Get the distributed angles
angles = distribute_angles(total_angle, num_motors)

# Function to simulate setting the angle for each motor
def set_angle(motor_id, angle):
    # This is where you would send the command to the motor driver/controller
    # For this example, we'll just print the command
    print(f"Setting motor {motor_id} to {angle} degrees")

# Function to move the robotic arm to the desired total angle
def move_robotic_arm(total_angle, num_motors):
    angles = distribute_angles(total_angle, num_motors)
    for i, angle in enumerate(angles):
        set_angle(i + 1, angle)

# Move the robotic arm to 180 degrees
move_robotic_arm(total_angle, num_motors)
