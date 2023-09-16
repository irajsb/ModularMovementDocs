# Vehicle Data Setup

In the **Vehicle Data Setup** module, you will configure essential vehicle data that plays a crucial role in defining your vehicle's behavior. This includes the torque curve, max RPM, gearbox settings, steering, and more. Let's delve into the essential components:

## Torque Curve and Max RPM

One of the fundamental aspects of a vehicle's performance is its torque curve and maximum RPM (Revolutions Per Minute). It's essential for a realistic engine simulation that the torque curve reaches zero or approaches zero around or before the maximum RPM. This aligns with the limitations of real-world engines.

To create a torque curve for your vehicle, you can reference an existing curve from a similar vehicle or use a curve that matches the characteristics of your specific vehicle. Copy and paste this curve into the engine for accurate representation.

## Gearbox Configuration

The gearbox configuration is another critical element of your vehicle setup. You can define an array of gears, where the gear with a ratio of 0 is considered idle. Gears before this point represent reverse, while gears after this point represent forward motion. Each gear has an RPM ratio for gear changes, ranging from 0 to 1.

It's important to note that the gear ratio is influenced by the differential ratio and the final drive ratio, which, in turn, is affected by the wheel radius. Tuning the differential ratio allows you to fine-tune the vehicle's power-to-maximum-speed ratio. If you notice that your RPM is changing at a rate different from your expectations, this parameter should be adjusted accordingly.

## Steering Curve

To enhance your vehicle's control and realism, it's recommended to implement a steering curve. This curve reduces the sensitivity of steering input relative to the vehicle's speed. You might have observed this phenomenon when driving your own vehicle, where minimal steering input is required at high speeds due to subconscious adjustments.

With these essential components and configurations, you can fine-tune your vehicle's behavior and performance to match your project's requirements. Each parameter plays a crucial role in creating an authentic and enjoyable vehicle simulation.


## Params and their explnatation Explanation



| Parameter                           | Type                                   | Explanation                                                                                     |
| ----------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------- |
| EngineTorqueCurve                   | FRuntimeFloatCurve                     | Torque curve in Newtons per Meter.                                                             |
| ZeroRpmWhenShifting                 | bool                                   | Set RPM to zero when shifting.                                                                 |
| IdleRpm                             | float                                  | Idle RPM (can be zero).                                                                         |
| MaxRpm                              | float                                  | Maximum RPM, generally where torque curve reaches zero torque.                                  |
| EngineInertia                       | float                                  | How fast the engine RPM can change, used to stabilize RPM ranges from 0 to 1.                   |
| GearBoxData                         | UModularGearBox (Instanced)            | Gearbox data for defining gears.                                                                |
| SuspensionTraceTypeQuery            | TEnumAsByte\<ETraceTypeQuery\>         | Suspension trace type.                                                                          |
| ScaleTireFrictionWithSurfaceAngle   | bool                                   | Divide available tire grip between drive wheels based on surface angle (realistic value is true). |
| ScaleDriveTorqueToNumberOfWheels    | bool                                   | Divide drive torque among the number of wheels touching the ground to simulate a differential. |
| SteerCurve                          | FRuntimeFloatCurve                     | Steering curve for controlling steering input relative to vehicle speed.                          |
| SteerType                           | TEnumAsByte\<EModularSteerType\>       | Steering method.                                                                                |
| TrackWidth                          | float                                  | Lateral distance between two wheels on the same axle.                                          |
| WheelBase                           | float                                  | Distance between two axles.                                                                    |
| SteerInputRise                      | float                                  | How fast the input should rise, multiplied by DeltaTime.                                       |
| SteerInputFall                      | float                                  | How fast the input should fall, multiplied by DeltaTime.                                       |
| CounterSteerMultiplier              | float                                  | Multiplier for input when the vehicle is sliding and trying to reorient itself.                |
| bReverseAsBrake                     | bool                                   | Brake input will put the vehicle in reverse once it has stopped.                                |
| WrongDirectionThreshold             | float                                  | Auto-brake when the vehicle's forward speed is opposite of player input by at least this much (cm/s). |
| StopThreshold                       | float                                  | Auto-brake when the absolute vehicle forward speed is less than this (cm/s).                    |
| IdleBrakeInput                      | float                                  | How much to press the brake when the player has released the throttle.                            |
| AIMaxSteerMultiplier                | float                                  | Multiplier for AI vehicles to make steering easier.                                            |
| ReverseThreshold                    | float                                  | Threshold for reversing based on dot product between forward vector and destination (-1 to 1). |
| TurnThreshold                       | float                                  | Threshold for slow steering based on dot product between forward vector and destination (-1 to 1). Should be higher than ReverseThreshold. |
| DesireSpeedNormal                   | float                                  | Desired speed when moving forward normally (km/h).                                             |
| DesireSpeedTurning                  | float                                  | Desired speed when turning towards a goal (should be small to steer fully).                      |
| DesireSpeedTurningAround            | float                                  | Desired speed when performing a U-turn (km/h).                                                  |
| DesireSpeedNearGoal                 | float                                  | Desired speed when near a goal, calculated based on distance (cm) and desired speed.            |
| NearGoalDistance                    | float                                  | Distance (cm) considered "near goal" to apply near goal speed.                                   |
| FullThrottleSpeed                   | float                                  | Speed difference that triggers flooring the gas.                                                |
| AITraceLength                       | float                                  | Length of the avoidance trace (cm).                                                            |
| AITraceSpeedMultiplier              | float                                  | Multiplier for trace length based on vehicle speed.                                             |
| VehicleFrontArea                    | float                                  | Frontal area for calculating air resistance (Meters^2).                                          |
| AirDensity                          | float                                  | Air density (typically equal to Earth's air density).                                           |
| AirDragCoefficient                  | float                                  | The drag coefficient for air resistance (dimensionless).                                        |
| NetworkMode                         | TEnumAsByte\<EVehicleNetworkMode\>     | Network mode for vehicle replication.                                                           |

These parameters will help you fine-tune your vehicles and define their behavior within your game. Adjust them to achieve the desired performance and realism.
