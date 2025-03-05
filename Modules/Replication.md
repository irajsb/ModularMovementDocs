# Wheel Setup

Since replication has progressed much since original version of UE that Modular Movement is based on. We've decided to use unreal's replication with some extentions for physics body.

Default replication params can cause the vehicle to be very shaky.

Here is my recommended params inside DefaultEngine.ini (It can be too strict probably more suitable for comp games as it will try to fix differences ASAP )

```[/Script/Engine.PhysicsSettings]
PhysicErrorCorrection=(PingExtrapolation=0.300000,PingLimit=100.000000,ErrorPerLinearDifference=0.100000,ErrorPerAngularDifference=0.100000,MaxRestoredStateError=1.000000,MaxLinearHardSnapDistance=2000.000000,PositionLerp=0.000000,AngleLerp=0.005000,LinearVelocityCoefficient=200.000000,AngularVelocityCoefficient=20.000000,ErrorAccumulationSeconds=0.500000,ErrorAccumulationDistanceSq=25.000000,ErrorAccumulationSimilarity=200.000000)
MaxSubstepDeltaTime=0.004167
MaxSubsteps=16
```