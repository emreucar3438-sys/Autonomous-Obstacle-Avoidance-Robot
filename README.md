# 🤖 Obstacle Avoiding Robot with Signal Processing

An autonomous robot that navigates by detecting obstacles using advanced signal processing techniques.

## 🎯 Features

- **Median Filter**: Removes sensor spikes and outliers
- **Exponential Moving Average (EMA)**: Smooths distance readings
- **Intelligent Decision Making**: Scans left and right to choose optimal path
- **Robust Navigation**: Handles noisy sensor data reliably

## 🔧 Hardware Requirements

- Arduino UNO/Nano
- HC-SR04 Ultrasonic Sensor
- SG90 Servo Motor
- L298N Motor Driver
- 2x DC Motors
- Chassis with wheels
- Power supply (batteries)

## 📊 Signal Processing Pipeline
```
Raw Sensor Data → Median Filter → EMA Filter → Clean Data → Decision Making
                  (spike removal)  (smoothing)
```

### Example:
```
Raw:      [10, 11, 150, 12, 11]  (150 is spike)
Median:   11
EMA:      11.2 (smoothed)
Decision: MOVE FORWARD ✓
```

## 🚀 How It Works

1. **Continuous Scanning**: Ultrasonic sensor measures distance ahead
2. **Signal Filtering**: 
   - Median filter removes random spikes
   - EMA smooths the signal over time
3. **Obstacle Detection**: If distance < 30cm, trigger avoidance
4. **Smart Turning**:
   - Scan right side
   - Scan left side
   - Turn towards the side with more free space

## 📈 Filter Parameters

- `FILTER_SIZE = 5`: Number of samples for median calculation
- `ALPHA = 0.3`: EMA smoothing factor
  - 0.1 = Very smooth, slow response
  - 0.5 = Balanced
  - 0.9 = Fast response, minimal smoothing

## 🔌 Pin Configuration

| Component | Arduino Pin |
|-----------|-------------|
| Ultrasonic Trigger | 12 |
| Ultrasonic Echo | 11 |
| Servo | 10 |
| Left Motor Forward | 5 |
| Left Motor Back | 6 |
| Right Motor Forward | 7 |
| Right Motor Back | 8 |

## 💡 Usage

1. Upload code to Arduino
2. Power on the robot
3. Place on flat surface
4. Robot will automatically start navigating

## 📝 License

MIT License - Feel free to use and modify

## 👤 Author

[Emre Uçar]  
