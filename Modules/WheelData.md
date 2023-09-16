# Wheel Setup

In the **Wheel Setup** module, we focus on configuring the wheels of your vehicles, a critical aspect for achieving realistic physics and behavior. Key parameters include wheel radius, length, stiffness, and various settings that determine how the wheels interact with the vehicle and the terrain.

## Wheel Essentials
```Ensure that your wheel mesh has no collision```
### Wheel Radius and Length

- **Wheel radius** determines the size of your vehicle's wheels, affecting both appearance and performance.
- **Wheel length** influences how the vehicle interacts with terrain and obstacles. Balancing these parameters is crucial for achieving the desired vehicle behavior.

### Wheel Stiffness

- **Wheel stiffness** is a fundamental parameter that should be tuned relative to your vehicle's mass. It's measured in Newtons per meter (N/m) and governs the wheel's response to forces, impacts, and terrain variations. Proper stiffness adjustment ensures realistic suspension and tire behavior.

### Wheel Placement

Ensuring correct wheel placement is essential for predictable vehicle behavior. Wheels should either be children of the simulated root component or the body of the vehicle. Alternatively, they should be positioned in a way that maintains their relative position to the vehicle's body, regardless of the situation.

### Attachment of Wheel Meshes

You have the flexibility to attach wheel meshes to the wheel components if necessary, enhancing the visual representation of your vehicle.

## Wheel Types

Here are some common ways to configure wheels, although you're not limited to these options:

- **Wheel with Static Mesh Child:** Suitable for vehicles like sports cars (as demonstrated in the example project).
- **Wheel with Skeletal Mesh Child:** Ideal for vehicles like tanks (KVtank in the example project) where complex animations are required.
- **Wheel with No Child:** Used in situations where wheels are part of the root component's skeleton, as seen in the HeavyTank example project.

Now, let's delve into the specific properties that you can configure for your wheel setups.

## Per Wheel data

Per wheel data allows you to change wheel specific data wihtout creating another setup for front or rear wheels

| Property                | Type                          | Explanation                                            |
| ----------------------- | ----------------------------- | ------------------------------------------------------ |
| AnimateChildComponent   | bool                          | Automatically animate child components (used for static mesh wheels). |
| ApplyDriveForce         | bool                          | Determine whether this wheel applies drive force.     |
| SteerScale              | float                         | Scale for wheel steering (can be negative for back wheel steering or less than 1). |
| AffectedByHandBrake     | bool                          | Determine if this wheel is affected by the handbrake. |


Now, let's proceed to configure the specific properties of the wheel setup.

## Wheel Setup Parameters


Here is a table of properties and their explanations for configuring wheel setups:

| Property               | Type                          | Explanation                                           |
| ---------------------- | ----------------------------- | ----------------------------------------------------- |
| SuspensionLength       | float                         | How much the wheels can drop in centimeters (cm).    |
| WheelRadius            | float                         | Trace wheel radius in centimeters (cm).               |
| SuspensionType         | TEnumAsByte\<ESuspensionType\> | Trace channel for the suspension.                     |
| WheelWidth             | float                         | Trace wheel width in centimeters (cm).               |
| WheelMass              | float                         | Wheel mass, affecting inertia and wheel speed changes. Adjust for stability if needed. |
| TraceStartOffset       | FVector                       | Offset to apply to the trace start location.          |
| SpringRate             | float                         | Force to apply for suspension in Newtons per meter (N/m). |
| DampingRebound         | float                         | Damping when the spring is being extended from compression (N.s/M). |
| DampingCompress        | float                         | Damping when the spring is being compressed (N.s/M).  |
| BrakeTorque            | float                         | Brake torque applied to the wheels.                  |
| HandBrakeTorque        | float                         | Hand brake torque applied to wheels with this enabled. |
| ABS                    | bool                          | Prevent wheels from locking while braking and try to maintain perfect grip. |
| TractionControl        | bool                          | Prevent the engine from spinning the wheels by reducing power and maintaining grip. |
| SteepSurfaceAssistance | float                         | Control how much power is retained when going uphill. 0 is physically realistic, 1 is no power loss. |
| SteeringMaxAngle       | float                         | Maximum steering angle in degrees.                   |
| SuspensionPivot        | float                         | Suspension pivot point, which rotates the suspension when dropping, used for off-road vehicles. |
| AnimSpeed              | float                         | Smooth the wheel location and rotation; set to 0 to disable smoothing. |
| TireModel              | UBaseTireModel (Instanced)     | Implementation of the tire model for the wheel.      |

These properties allow you to customize the behavior and characteristics of your vehicle's wheels to achieve the desired performance and realism.
