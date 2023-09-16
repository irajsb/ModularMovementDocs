# Tire Models

In the **Tire Models** module, you can choose from four distinct tire models, each designed to cater to different needs and preferences in your vehicle simulation. The selection of a tire model significantly influences the behavior of your vehicle's tires and how they interact with the environment.

## Default Tire Model

The **Default Tire Model** is a realistic tire simulation that provides a high degree of accuracy. It is recommended for use with physics substepping to capture fine details of tire behavior. This model utilizes a traction equation to determine tire forces. What sets it apart is the level of control it offers, allowing you to fine-tune tire frictions using custom graphs.

## Pacejka Tire Model

The **Pacejka Tire Model** is also a realistic option and is widely known in the automotive simulation field. It generates tire force curves based on specific constants within the Pacejka formula. This model, like the Default Tire Model, delivers a high degree of realism and is suitable for physics substepping.

## Arcade Tire Model

The **Arcade Tire Model** offers a simplified approach with linear friction characteristics, making it easier to tune for more arcade-style vehicle behavior. This model provides a smoother and more predictable driving experience, ideal for games where realism takes a backseat to fun and accessibility.

## Tank Tire Model

The **Tank Tire Model** is similar to the Arcade Tire Model but applies forces based on tracks, mimicking the movement of a tank. If your project involves vehicles with tank-like tracks, this model is the most suitable choice.

Choosing the right tire model is a crucial step in achieving the desired balance between realism and gameplay experience in your vehicle simulation. Consider your project's goals and requirements to make an informed decision on which tire model best fits your needs.


## Default Tire Model Parameters

| Property                       | Type                 | Explanation                                                  |
| ------------------------------ | -------------------- | ------------------------------------------------------------ |
| AutoGenerateGraph              | bool                 | Enables the automatic generation of tire graphs using specified min and max parameters. |
| MinFrictionForce               | float                | The minimum friction force for auto-generated graphs. (Edit condition: AutoGenerateGraph) |
| MaxFrictionForce               | float                | The maximum friction force for auto-generated graphs. (Edit condition: AutoGenerateGraph) |
| LongitudinalGripCurve          | FRuntimeFloatCurve   | Defines the longitudinal grip curve for the tire.           |
| AutoGenerateTheLateralGraph    | bool                 | Enables the automatic generation of lateral tire graphs using specified min and max parameters. |
| MinFrictionLateralForce        | float                | The minimum lateral friction force for auto-generated graphs. (Edit condition: AutoGenerateTheLateralGraph) |
| MaxFrictionLateralForce        | float                | The maximum lateral friction force for auto-generated graphs. (Edit condition: AutoGenerateTheLateralGraph) |
| LateralGripCurve               | FRuntimeFloatCurve   | Defines the lateral grip curve for the tire.                |

These properties allow you to configure the Default Tire Model to precisely control tire behavior and friction characteristics for your vehicles.


## Pacejka Tire Model Parameters

### FPacejkaConstants

The FPacejkaConstants struct contains the following properties for configuring the Pacejka Tire Model:

| Property  | Type   | Explanation                                      |
| --------- | ------ | ------------------------------------------------ |
| B         | float  | Stiffness parameter affecting tire behavior.     |
| C         | float  | Shape parameter influencing tire characteristics. |
| E         | float  | Curvature parameter affecting tire response.     |
| D         | float  | Peak Force parameter controlling tire forces.    |

### Long

The Long property represents the longitudinal Pacejka constants used for the tire model. It allows you to configure the Pacejka constants specific to the longitudinal (forward/backward) tire behavior.

### Lat

The Lat property represents the lateral (sideways) Pacejka constants used for the tire model. It provides a set of default Pacejka constants but can be customized as needed to control the lateral tire behavior.

These properties enable you to fine-tune the Pacejka Tire Model, adjusting the constants to achieve the desired tire behavior and characteristics for your vehicles.



## Arcade Tire Model Parameters

| Property                     | Type               | Explanation                                                  |
| ---------------------------- | ------------------ | ------------------------------------------------------------ |
| FrictionMultiplierLongitudinal | float              | Friction multiplier on the forward axis of the wheel.        |
| AutoGenerateTheGraph          | bool               | Enables the generation of a general tire graph based on the specified values below. |
| MinFrictionLateralForce       | float              | Minimum friction force when traction is lost laterally. (Edit condition: AutoGenerateTheGraph) |
| MaxFrictionLateralForce       | float              | Maximum friction force when the wheel has perfect lateral grip. (Edit condition: AutoGenerateTheGraph) |
| LateralGripCurve              | FRuntimeFloatCurve | Defines the lateral force curve for the tire.                |
| FrictionEllipse               | FVector2D          | A vector that combines the lateral and longitudinal frictions, allowing them to affect each other. For example, when the wheels are locked by the handbrake, this value can be used to control the friction ellipse. |

These properties enable you to configure the Arcade Tire Model to control friction behavior and characteristics for your vehicles, providing an easier-to-tune, arcade-style tire simulation.


## Tank Tire Model Parameters

| Property                     | Type   | Explanation                                                  |
| ---------------------------- | ------ | ------------------------------------------------------------ |
| FrictionMultiplierLongitudinal | float  | Longitudinal friction multiplier for the tire.               |
| FrictionMultiplierLateral    | float  | Lateral friction multiplier for the tire.                    |
| SprocketRadius               | float  | Radius of the sprocket for the tire.                         |
| UseBrakesForSteering         | bool   | A flag indicating whether brakes are used for steering.       |
| NormalizedSteeringBrakeInput | float  | Normalized input for steering with brakes, ranging from 0.0 (no steering) to 1.0 (full steering). |

These properties allow you to configure the Tank Tire Model to control the behavior and characteristics of tank-like vehicles, including sprocket radius, steering with brakes, and friction multipliers for both longitudinal and lateral tire behavior.