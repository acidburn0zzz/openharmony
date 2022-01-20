# 传感器

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> 本模块首批接口从API version 8开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。


## 导入模块

```
import sensor from '@ohos.sensor';
```


## 权限列表

计步器：ohos.permission.ACTIVITY_MOTION

心率：ohos.permission.READ_HEALTH_DATA

加速度：ohos.permission.ACCELEROMETER

陀螺仪：ohos.permission.GYROSCOPE


## sensor.on(SensorType.SENSOR_TYPE_ID_ACCELEROMETER)

on(type: SensorType.SENSOR_TYPE_ID_ACCELEROMETER, callback: AsyncCallback&lt;AccelerometerResponse&gt;,options?: Options): void


监听加速度传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。


- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的加速度传感器类型为SENSOR_TYPE_ID_ACCELEROMETER。 |
  | callback | AsyncCallback&lt;[AccelerometerResponse](#accelerometerresponse)&gt; | 是 | 注册加速度传感器的回调函数，上报的数据类型为AccelerometerResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);    
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    },
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_LINEAR_ACCELERATION)

on(type:SensorType.SENSOR_TYPE_ID_LINEAR_ACCELERATION,callback:AsyncCallback&lt;LinearAccelerometerResponse&gt;, options?: Options): void

监听线性加速度传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的线性加速度传感器类型为SENSOR_TYPE_ID_LINEAR_ACCELERATION。 |
  | callback | AsyncCallback&lt;[LinearAccelerometerResponse](#linearaccelerometerresponse)&gt; | 是 | 注册线性加速度传感器的回调函数，上报的数据类型为LinearAccelerometerResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type:SensorType.SENSOR_TYPE_ID_LINEAR_ACCELEROMETER,function(error,data){    
     if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED)

on(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED,callback:AsyncCallback&lt;AccelerometerUncalibratedResponse&gt;, options?: Options): void

监听未校准加速度计传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的未校准加速度计传感器类型为SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[AccelerometerUncalibratedResponse](#accelerometeruncalibratedresponse)&gt; | 是 | 注册未校准加速度计传感器的回调函数，上报的数据类型为AccelerometerUncalibratedResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
      console.info('X-coordinate bias: ' + data.biasX);
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_GRAVITY)

on(type: SensorType.SENSOR_TYPE_ID_GRAVITY, callback: AsyncCallback&lt;GravityResponse&gt;,options?: Options): void

监听重力传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的重力传感器类型为SENSOR_TYPE_ID_GRAVITY。 |
  | callback | AsyncCallback&lt;[GravityResponse](#gravityresponse)&gt; | 是 | 注册重力传感器的回调函数，上报的数据类型为GravityResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type:SensorType.SENSOR_TYPE_ID_GRAVITY,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x); 
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_GYROSCOPE)

on(type: SensorType.SENSOR_TYPE_ID_GYROSCOPE, callback: AsyncCallback&lt;GyroscopeResponse&gt;, options?: Options): void

监听陀螺仪传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的陀螺仪传感器类型为SENSOR_TYPE_ID_GYROSCOPE。 |
  | callback | AsyncCallback&lt;[GyroscopeResponse](#gyroscoperesponse)&gt; | 是 | 注册陀螺仪传感器的回调函数，上报的数据类型为GyroscopeResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type:SensorType.SENSOR_TYPE_ID_GUROSCOPE,function(error,data){    
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x); 
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED)

on(type:SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED,callback:AsyncCallback&lt;GyroscopeUncalibratedResponse&gt;, options?: Options): void

监听未校准陀螺仪传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的未校准陀螺仪传感器类型为SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[GyroscopeUncalibratedResponse](#gyroscopeuncalibratedresponse)&gt; | 是 | 注册未校准陀螺仪传感器的回调函数，上报的数据类型为GyroscopeUncalibratedResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);  
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
      console.info('X-coordinate bias: ' + data.biasX); 
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION)

on(type: SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION, callback: AsyncCallback&lt;SignificantMotionResponse&gt;, options?: Options): void

监听大幅动作传感器数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的大幅动作传感器类型为SENSOR_TYPE_ID_SIGNIFICANT_MOTION。 |
  | callback | AsyncCallback&lt;[SignificantMotionResponse](#significantmotionresponse)&gt; | 是 | 注册有效运动传感器的回调函数，上报的数据类型为SignificantMotionResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Scalar data: ' + data.scalar);
    }
    {interval: 10000000}      
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION)

on(type: SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION, callback: AsyncCallback&lt;PedometerDetectResponse&gt;, options?: Options): void

监听计步检测传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的计步检测传感器类型为SENSOR_TYPE_ID_PEDOMETER_DETECTION。 |
  | callback | AsyncCallback&lt;[PedometerDetectResponse](#pedometerdetectresponse)&gt; | 是 | 注册计步检测传感器的回调函数，上报的数据类型为PedometerDetectResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION,function(error,data){
      if (error) {
          console.error(""Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Scalar data: ' + data.scalar);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_PEDOMETER)

on(type: SensorType.SENSOR_TYPE_ID_PEDOMETER, callback: AsyncCallback&lt;PedometerResponse&gt;, options?: Options): void

监听计步传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的计步传感器类型为SENSOR_TYPE_ID_PEDOMETER。 |
  | callback | AsyncCallback&lt;[PedometerResponse](#pedometerresponse)&gt; | 是 | 注册计步传感器的回调函数，上报的数据类型为PedometerResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_PEDOMETER,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Steps: ' + data.steps);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE)

on(type:SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE,callback:AsyncCallback&lt;AmbientTemperatureResponse&gt;,  options?: Options): void

监听环境温度传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的环境温度传感器类型为SENSOR_TYPE_ID_AMBIENT_TEMPERATURE。 |
  | callback | AsyncCallback&lt;[AmbientTemperatureResponse](#ambienttemperatureresponse)&gt; | 是 | 注册环境温度传感器的回调函数，上报的数据类型为AmbientTemperatureResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Temperature: ' + data.temperature);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD)

on(type: SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD, callback: AsyncCallback&lt;MagneticFieldResponse&gt;,options?: Options): void

监听磁场传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的磁场传感器类型为SENSOR_TYPE_ID_MAGNETIC_FIELD。 |
  | callback | AsyncCallback&lt;[MagneticFieldResponse](#magneticfieldresponse)&gt; | 是 | 注册磁场传感器的回调函数，上报的数据类型为MagneticFieldResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD,function(error,data){    
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED)

on(type:SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED,callback:AsyncCallback&lt;MagneticFieldUncalibratedResponse&gt;, options: Options): void

监听未校准磁场传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的未校准磁场传感器类型为SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[MagneticFieldUncalibratedResponse](#magneticfielduncalibratedresponse)&gt; | 是 | 注册未校准磁场传感器的回调函数，上报的数据类型为MagneticFieldUncalibratedResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  ensor.on(type: SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);    
      console.info('Y-coordinate component: ' + data.y);    
      console.info('Z-coordinate component: ' + data.z);    
      console.info('X-coordinate bias: ' + data.biasX);    
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
    {interval: 10000000}   //设置数据的上报频率。
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_PROXIMITY)

on(type: SensorType.SENSOR_TYPE_ID_PROXIMITY, callback: AsyncCallback&lt;ProximityResponse&gt;,options?: Options): void

监听接近光传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的接近光传感器类型为SENSOR_TYPE_ID_PROXIMITY。 |
  | callback | AsyncCallback&lt;[ProximityResponse](#proximityresponse)&gt; | 是 | 注册接近光传感器的回调函数，上报的数据类型为ProximityResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_PROXIMITY,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Distance: ' + data.distance);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_HUMIDITY)

on(type: SensorType.SENSOR_TYPE_ID_HUMIDITY, callback: AsyncCallback&lt;HumidityResponse&gt;,options?: Options): void

监听湿度传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的湿度传感器类型为SENSOR_TYPE_ID_HUMIDITY。 |
  | callback | AsyncCallback&lt;[HumidityResponse](#humidityresponse)&gt; | 是 | 注册湿度传感器的回调函数，上报的数据类型为HumidityResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_HUMIDITY,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Humidity: ' + data.humidity);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_BAROMETER)

on(type: SensorType.SENSOR_TYPE_ID_BAROMETER, callback: AsyncCallback&lt;BarometerResponse&gt;,options?: Options): void

监听气压计传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的气压计传感器类型为SENSOR_TYPE_ID_BAROMETER。 |
  | callback | AsyncCallback&lt;[BarometerResponse](#barometerresponse)&gt; | 是 | 注册气压计传感器的回调函数，上报的数据类型为BarometerResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_BAROMETER,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Atmospheric pressure: ' + data.pressure);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_HALL)

on(type: SensorType.SENSOR_TYPE_ID_HALL, callback: AsyncCallback&lt;HallResponse&gt;, options?: Options): void

监听霍尔传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的霍尔传感器类型为SENSOR_TYPE_ID_HALL。 |
  | callback | AsyncCallback&lt;[HallResponse](#hallresponse)&gt; | 是 | 注册霍尔传感器的回调函数，上报的数据类型为&nbsp;HallResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_HALL,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Status: ' + data.status);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT)

on(type: SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT, callback: AsyncCallback&lt;LightResponse&gt;, options?: Options): void

监听环境光传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的环境光传感器类型为SENSOR_TYPE_ID_AMBIENT_LIGHT。 |
  | callback | AsyncCallback&lt;[LightResponse](#lightresponse)&gt; | 是 | 注册环境光传感器的回调函数，上报的数据类型为LightResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT,function(error,data){
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info(''Illumination: ' + data.intensity);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_ORIENTATION)

on(type: SensorType.SENSOR_TYPE_ID_ORIENTATION, callback: AsyncCallback&lt;OrientationResponse&gt;, options?: Options): void

监听方向传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的方向传感器类型为SENSOR_TYPE_ID_ORIENTATION |
  | callback | AsyncCallback&lt;[OrientationResponse](#orientationresponse)&gt; | 是 | 注册方向传感器的回调函数，上报的数据类型为OrientationResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_ORIENTATION,function(error,data){    
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR)

on(type:SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR,callback:AsyncCallback&lt;RotationVectorResponse&gt;,options?: Options): void

监听旋转矢量传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的旋转矢量传感器类型为SENSOR_TYPE_ID_ROTATION_VECTOR。 |
  | callback | AsyncCallback&lt;[RotationVectorResponse](#rotationvectorresponse)&gt; | 是 | 注册旋转矢量传感器的回调函数，上报的数据类型为RotationVectorResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR,function(error,data){    
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
    {interval: 10000000}
  );
  ```


## sensor.on(SensorType.SENSOR_TYPE_ID_WEAR_DETECTION)

on(type: SensorType.SENSOR_TYPE_ID_WEAR_DETECTION, callback: AsyncCallback&lt;WearDetectionResponse&gt;,options?: Options): void

监听佩戴检测传感器的数据变化。如果多次调用该接口，仅最后一次调用生效。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要订阅的佩戴检测传感器类型为SENSOR_TYPE_ID_WEAR_DETECTION。 |
  | callback | AsyncCallback&lt;[WearDetectionResponse](#weardetectionresponse)&gt; | 是 | 注册佩戴检测传感器的回调函数，上报的数据类型为WearDetectionResponse。 |
  | options | [Options](#options) | 否 | 可选参数列表，设置上报频率，默认值为200000000ns。 |

- 示例：
  ```
  sensor.on(type: SensorType.SENSOR_TYPE_ID_WEAR_DETECTION,function(error,data){    
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Wear status: ' + data.value);
    }
    {interval: 10000000}
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_ACCELEROMETER)

once(type: SensorType.SENSOR_TYPE_ID_ACCELEROMETER, callback: AsyncCallback&lt;AccelerometerResponse&gt;): void

监听加速度传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 加速度传感器类型为SENSOR_TYPE_ID_ACCELEROMETER。 |
  | callback | AsyncCallback&lt;[AccelerometerResponse](#accelerometerresponse)&gt; | 是 | 注册一次加速度传感器的回调函数，上报的数据类型为AccelerometerResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_LINEAR_ACCELERATION)

once(type:SensorType.SENSOR_TYPE_ID_LINEAR_ACCELERATION,callback:AsyncCallback&lt;LinearAccelerometerResponse&gt;): void

监听线性加速度传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 线性加速度传感器类型为SENSOR_TYPE_ID_LINEAR_ACCELERATION。 |
  | callback | AsyncCallback&lt;[LinearAccelerometerResponse](#linearaccelerometerresponse)&gt; | 是 | 注册一次线性加速度传感器的回调函数，上报的数据类型为LinearAccelerometerResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_LINEAR_ACCELERATION, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED)

once(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED,callback:AsyncCallback&lt;AccelerometerUncalibratedResponse&gt;): void

监听未校准加速度传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 未校准加速度传感器类型为SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[AccelerometerUncalibratedResponse](#accelerometeruncalibratedresponse)&gt; | 是 | 注册一次未校准加速度传感器的回调函数，上报的数据类型为AccelerometerUncalibratedResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
      console.info('X-coordinate bias: ' + data.biasX);
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_GRAVITY)

once(type: SensorType.SENSOR_TYPE_ID_GRAVITY, callback: AsyncCallback&lt;GravityResponse&gt;): void

监听重力传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 重力传感器类型为SENSOR_TYPE_ID_GRAVITY。 |
  | callback | AsyncCallback&lt;[GravityResponse](#gravityresponse)&gt; | 是 | 注册一次重力传感器的回调函数，上报的数据类型为GravityResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_GRAVITY, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_GYROSCOPE)

once(type: SensorType.SENSOR_TYPE_ID_GYROSCOPE, callback: AsyncCallback&lt;GyroscopeResponse&gt;): void

监听陀螺仪传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 陀螺仪传感器类型为SENSOR_TYPE_ID_GYROSCOPE。 |
  | callback | AsyncCallback&lt;[GyroscopeResponse](#gyroscoperesponse)&gt; | 是 | 注册一次陀螺仪传感器的回调函数，上报的数据类型为GyroscopeResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_GYROSCOPE, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED)

once(type:SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED,callback:AsyncCallback&lt;GyroscopeUncalibratedResponse&gt;): void

监听未校准陀螺仪传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 未校准陀螺仪传感器类型为SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[GyroscopeUncalibratedResponse](#gyroscopeuncalibratedresponse)&gt; | 是 | 注册一次未校准陀螺仪传感器的回调函数，上报的数据类型为GyroscopeUncalibratedResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
      console.info('X-coordinate bias: ' + data.biasX);
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION)

once(type: SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION,callback:AsyncCallback&lt;SignificantMotionResponse&gt;): void

监听有效运动传感器的数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 有效运动传感器类型为SENSOR_TYPE_ID_SIGNIFICANT_MOTION。 |
  | callback | AsyncCallback&lt;[SignificantMotionResponse](#significantmotionresponse)&gt; | 是 | 注册一次有效运动传感器的回调函数，上报的数据类型为SignificantMotionResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_SIGNIFICANT_MOTION, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Scalar data: ' + data.scalar);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION)

once(type:SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION,callback:AsyncCallback&lt;PedometerDetectResponse&gt;): void

监听计步检测传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 计步检测传感器类型为SENSOR_TYPE_ID_PEDOMETER_DETECTION。 |
  | callback | AsyncCallback&lt;[PedometerDetectResponse](#pedometerdetectresponse)&gt; | 是 | 注册一次计步检测传感器的回调函数，上报的数据类型为PedometerDetectResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_PEDOMETER_DETECTION, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Scalar data: ' + data.scalar);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_PEDOMETER)

once(type: SensorType.SENSOR_TYPE_ID_PEDOMETER, callback: AsyncCallback&lt;PedometerResponse&gt;): void

监听计步器传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 计步传感器类型为SENSOR_TYPE_ID_PEDOMETER。 |
  | callback | AsyncCallback&lt;[PedometerResponse](#pedometerresponse)&gt; | 是 | 注册一次计步传感器的回调函数，上报的数据类型为PedometerResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_PEDOMETER, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Steps: ' + data.steps);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE)

once(type:SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE,callback:AsyncCallback&lt;AmbientTemperatureResponse&gt;): void

监听环境温度传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 环境温度传感器类型为SENSOR_TYPE_ID_AMBIENT_TEMPERATURE。 |
  | callback | AsyncCallback&lt;[AmbientTemperatureResponse](#ambienttemperatureresponse)&gt; | 是 | 注册一次环境温度传感器的回调函数，上报的数据类型为AmbientTemperatureResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_AMBIENT_TEMPERATURE, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Temperature: ' + data.temperature);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD)

once(type: SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD, callback: AsyncCallback&lt;MagneticFieldResponse&gt;): void

监听磁场传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 磁场传感器类型为SENSOR_TYPE_ID_MAGNETIC_FIELD。 |
  | callback | AsyncCallback&lt;[MagneticFieldResponse](#magneticfieldresponse)&gt; | 是 | 注册一次磁场传感器的回调函数，上报的数据类型为MagneticFieldResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED)

once(type:SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED,callback:AsyncCallback&lt;MagneticFieldUncalibratedResponse&gt;): void

监听未校准磁场传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 未校准磁场传感器类型为SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED。 |
  | callback | AsyncCallback&lt;[MagneticFieldUncalibratedResponse](#magneticfielduncalibratedresponse)&gt; | 是 | 注册一次未校准磁场传感器的回调函数，上报的数据类型为MagneticFieldUncalibratedResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
      console.info('X-coordinate bias: ' + data.biasX);
      console.info('Y-coordinate bias: ' + data.biasY);
      console.info('Z-coordinate bias: ' + data.biasZ);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_PROXIMITY)

once(type: SensorType.SENSOR_TYPE_ID_PROXIMITY, callback: AsyncCallback&lt;ProximityResponse&gt;): void

监听接近光传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 接近光传感器类型为SENSOR_TYPE_ID_PROXIMITY。 |
  | callback | AsyncCallback&lt;[ProximityResponse](#proximityresponse)&gt; | 是 | 注册一次接近光传感器的回调函数，上报的数据类型为ProximityResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_PROXIMITY, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Distance: ' + data.distance);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_HUMIDITY)

once(type: SensorType.SENSOR_TYPE_ID_HUMIDITY, callback: AsyncCallback&lt;HumidityResponse&gt;): void

监听湿度传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 湿度传感器类型为SENSOR_TYPE_ID_HUMIDITY。 |
  | callback | AsyncCallback&lt;[HumidityResponse](#humidityresponse)&gt; | 是 | 注册一次湿度传感器的回调函数，上报的数据类型为HumidityResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_HUMIDITY, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Humidity: ' + data.humidity);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_BAROMETER)

once(type: SensorType.SENSOR_TYPE_ID_BAROMETER, callback: AsyncCallback&lt;BarometerResponse&gt;): void

监听气压计传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 气压计传感器类型为SENSOR_TYPE_ID_BAROMETER。 |
  | callback | AsyncCallback&lt;[BarometerResponse](#barometerresponse)&gt; | 是 | 注册一次气压计传感器的回调函数，上报的数据类型为BarometerResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_BAROMETER, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Atmospheric pressure: ' + data.pressure);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_HALL)

once(type: SensorType.SENSOR_TYPE_ID_HALL, callback:   AsyncCallback&lt;HallResponse&gt;): void

监听霍尔传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 霍尔传感器类型为SENSOR_TYPE_ID_HALL。 |
  | callback | AsyncCallback&lt;[HallResponse](#hallresponse)&gt; | 是 | 注册一次霍尔传感器的回调函数，上报的数据类型为HallResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_HALL, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('Status: ' + data.status);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT)

once(type: SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT, callback: AsyncCallback&lt;LightResponse&gt;): void

监听环境光传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 环境光传感器类型为SENSOR_TYPE_ID_AMBIENT_LIGHT。 |
  | callback | AsyncCallback&lt;[LightResponse](#lightresponse)&gt; | 是 | 注册一次环境光传感器的回调函数，上报的数据类型为LightResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_AMBIENT_LIGHT, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info(''Illumination: ' + data.intensity);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_ORIENTATION)

once(type: SensorType.SENSOR_TYPE_ID_ORIENTATION, callback: AsyncCallback&lt;OrientationResponse&gt;): void

监听方向传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 方向传感器类型为SENSOR_TYPE_ID_ORIENTATION。 |
  | callback | AsyncCallback&lt;[OrientationResponse](#orientationresponse)&gt; | 是 | 注册一次方向传感器的回调函数，上报的数据类型为OrientationResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_ORIENTATION, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR)

once(type: SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR, callback: AsyncCallback&lt;RotationVectorResponse&gt;): void

监听旋转矢量传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 旋转矢量传感器类型为SENSOR_TYPE_ID_ROTATION_VECTOR。 |
  | callback | AsyncCallback&lt;[RotationVectorResponse](#rotationvectorresponse)&gt; | 是 | 注册一次旋转矢量传感器的回调函数，上报的数据类型为RotationVectorResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_ROTATION_VECTOR, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info('X-coordinate component: ' + data.x);
      console.info('Y-coordinate component: ' + data.y);
      console.info('Z-coordinate component: ' + data.z);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_HEART_RATE)

once(type: SensorType.SENSOR_TYPE_ID_HEART_RATE, callback: AsyncCallback&lt;HeartRateResponse&gt;): void

监听心率传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 心率传感器类型为SENSOR_TYPE_ID_HEART_RATE。 |
  | callback | AsyncCallback&lt;[HeartRateResponse](#heartrateresponse)&gt; | 是 | 注册一次心率传感器的回调函数，上报的数据类型为HeartRateResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_HEART_RATE, function(error, data) {
      if (error) {
          console.error("Subscription failed. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info("Heart rate: " + data.heartRate);
    }
  );
  ```


## sensor.once(SensorType.SENSOR_TYPE_ID_WEAR_DETECTION)

once(type: SensorType.SENSOR_TYPE_ID_WEAR_DETECTION, callback: AsyncCallback&lt;WearDetectionResponse&gt;): void

监听佩戴检测传感器数据变化一次。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 佩戴检测传感器类型为SENSOR_TYPE_ID_WEAR_DETECTION。 |
  | callback | AsyncCallback&lt;[WearDetectionResponse](#weardetectionresponse)&gt; | 是 | 注册一次穿戴检测传感器的回调函数，上报的数据类型为WearDetectionResponse。 |

- 示例：
  ```
  sensor.once(type:SensorType.SENSOR_TYPE_ID_WEAR_DETECTION, function(error, data) {
      if (error) {
          console.error("Failed to register data, error code is" + error.code + ", message: " + error.message);
          return;
      }
      console.info("Wear status: "+ data.value);
    }
  );
  ```


## sensor.off

off(type: SensorType, callback?: AsyncCallback&lt;void&gt;): void

取消订阅传感器数据。

- 参数：
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | type | [SensorType](#sensortype) | 是 | 要取消订阅的传感器类型。 |
  | callback | AsyncCallback&lt;void&gt; | 是 | 取消订阅的传感器的回调函数，表示接口调用是否成功。 |

- 示例：
  ```
  sensor.off(type:SensorType.SENSOR_TYPE_ID_ACCELEROMETER, function(error) {
      if (error) {
          console.error("Failed to unsubscribe from acceleration sensor data. Error code: " + error.code + "; message: " + error.message);
          return;
      }
      console.info("Succeeded in unsubscribing from acceleration sensor data.");
    }
  );
  
  ```


## sensor.getGeomagneticField

getGeomagneticField(locationOptions: LocationOptions, timeMillis: number, callback: AsyncCallback&lt;GeomagneticResponse&gt;): void

获取地球上特定位置的地磁场。

- 参数
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | locationOptions | [LocationOptions](#locationoptions) | 是 | 地理位置。 |
  | timeMillis | number | 是 | 表示获取磁偏角的时间，单位为毫秒。 |
  | callback | AsyncCallback&lt;[GeomagneticResponse](#geomagneticresponse)&gt; | 是 | 返回磁场信息。 |

- 示例
  ```
  sensor.getGeomagneticField([80, 0, 0], {'timeMillis':1580486400000}, function(err, data)  {
      if (err) {
          console.error('Operation failed. Error code: ' + err.code + '; message: ' + err.message);
          return;
      }
      console.info('sensor_getGeomagneticField_promise x: ' + data.x + ',y: ' + data.y + ',z: ' +
  	             data.z + ',geomagneticDip: ' + data.geomagneticDip + ',deflectionAngle: ' + data.deflectionAngle +
  		     ',levelIntensity: ' + data.levelIntensity + ',totalIntensity: ' + data.totalIntensity);
  });
  ```


## sensor.getGeomagneticField

getGeomagneticField(locationOptions: LocationOptions, timeMillis: number): Promise&lt;GeomagneticResponse&gt;

获取地球上特定位置的地磁场。

- 参数
  | 参数名 | 类型 | 必填 | 说明 |
  | -------- | -------- | -------- | -------- |
  | locationOptions | [LocationOptions](#locationoptions) | 是 | 地理位置。 |
  | timeMillis | number | 是 | 表示获取磁偏角的时间，单位为毫秒。 |

- 返回值
  | 类型 | 说明 |
  | -------- | -------- |
  | Promise&lt;[GeomagneticResponse](#geomagneticresponse)&gt; | 返回磁场信息。 |

- 示例
  ```
  const promise = sensor.getGeomagneticField([80, 0, 0], {'timeMillis':1580486400000});
      promise.then((data) => {
          console.info('sensor_getGeomagneticField_promise x: ' + data.x + ',y: ' + data.y + ',z: ' +
  	             data.z + ',geomagneticDip: ' + data.geomagneticDip + ',deflectionAngle: ' + data.deflectionAngle +
  		     ',levelIntensity: ' + data.levelIntensity + ',totalIntensity: ' + data.totalIntensity);
      }).catch((reason) => {
          console.info('Operation failed.');
  })
  ```


## SensorType

表示要订阅或取消订阅的传感器类型。


| 名称 | 默认值 | 说明 |
| -------- | -------- | -------- |
| SENSOR_TYPE_ID_ACCELEROMETER | 1 | 加速度传感器。 |
| SENSOR_TYPE_ID_GYROSCOPE | 2 | 陀螺仪传感器。 |
| SENSOR_TYPE_ID_AMBIENT_LIGHT | 5 | 环境光传感器。 |
| SENSOR_TYPE_ID_MAGNETIC_FIELD | 6 | 磁场传感器。 |
| SENSOR_TYPE_ID_BAROMETER | 8 | 气压计传感器。 |
| SENSOR_TYPE_ID_HALL | 10 | 霍尔传感器。 |
| SENSOR_TYPE_ID_PROXIMITY | 12 | 接近光传感器。 |
| SENSOR_TYPE_ID_HUMIDITY | 13 | 湿度传感器。 |
| SENSOR_TYPE_ID_ORIENTATION | 256 | 方向传感器。 |
| SENSOR_TYPE_ID_GRAVITY | 257 | 重力传感器。 |
| SENSOR_TYPE_ID_LINEAR_ACCELERATION | 258 | 线性加速度传感器。 |
| SENSOR_TYPE_ID_ROTATION_VECTOR | 259 | 旋转矢量传感器。 |
| SENSOR_TYPE_ID_AMBIENT_TEMPERATURE | 260 | 环境温度传感器。 |
| SENSOR_TYPE_ID_MAGNETIC_FIELD_UNCALIBRATED | 261 | 未校准磁场传感器。 |
| SENSOR_TYPE_ID_GYROSCOPE_UNCALIBRATED | 263 | 未校准陀螺仪传感器。 |
| SENSOR_TYPE_ID_SIGNIFICANT_MOTION | 264 | 有效运动传感器。 |
| SENSOR_TYPE_ID_PEDOMETER_DETECTION | 265 | 计步检测传感器。 |
| SENSOR_TYPE_ID_PEDOMETER | 266 | 计步传感器。 |
| SENSOR_TYPE_ID_HEART_RATE | 278 | 心率传感器。 |
| SENSOR_TYPE_ID_WEAR_DETECTION | 280 | 佩戴检测传感器。 |
| SENSOR_TYPE_ID_ACCELEROMETER_UNCALIBRATED | 281 | 未校准加速度计传感器。 |


## Response

传感器数据的时间戳。

| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| timestamp | number | 是 | 是 | 传感器数据上报的时间戳。 |


## AccelerometerResponse

加速度传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 施加在设备x轴的加速度，单位 : m/s2。 |
| y | number | 是 | 是 | 施加在设备y轴的加速度，单位 : m/s2。 |
| z | number | 是 | 是 | 施加在设备z轴的加速度，单位 : m/s2。 |


## LinearAccelerometerResponse

线性加速度传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 施加在设备x轴的线性加速度，单位 : m/s2。 |
| y | number | 是 | 是 | 施加在设备y轴的线性加速度，单位 : m/s2。 |
| z | number | 是 | 是 | 施加在设备z轴的线性加速度，单位 : m/s2。 |


## AccelerometerUncalibratedResponse

未校准加速度计传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 施加在设备x轴未校准的加速度，单位 : m/s2。 |
| y | number | 是 | 是 | 施加在设备y轴未校准的加速度，单位 : m/s2。 |
| z | number | 是 | 是 | 施加在设备z轴未校准的加速度，单位 : m/s2。 |
| biasX | number | 是 | 是 | 施加在设备x轴未校准的加速度偏量，单位 : m/s2。 |
| biasY | number | 是 | 是 | 施加在设备上y轴未校准的加速度偏量，单位 : m/s2。 |
| biasZ | number | 是 | 是 | 施加在设备z轴未校准的加速度偏量，单位 : m/s2。 |


## GravityResponse

重力传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 施加在设备x轴的重力加速度，单位 : m/s2。 |
| y | number | 是 | 是 | 施加在设备y轴的重力加速度，单位 : m/s2。 |
| z | number | 是 | 是 | 施加在设备z轴的重力加速度，单位 : m/s2。 |


## OrientationResponse

方向传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 设备围绕x轴的旋转角度，单位 : rad。 |
| y | number | 是 | 是 | 设备围绕y轴的旋转角度，单位 : rad。 |
| z | number | 是 | 是 | 设备围绕z轴的旋转角度，单位 : rad。 |


## RotationVectorResponse

旋转矢量传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 旋转矢量x轴分量。 |
| y | number | 是 | 是 | 旋转矢量y轴分量。 |
| z | number | 是 | 是 | 旋转矢量z轴分量。 |


## GyroscopeResponse

陀螺仪传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 设备x轴的旋转角速度，单位rad/s。 |
| y | number | 是 | 是 | 设备y轴的旋转角速度，单位rad/s。 |
| z | number | 是 | 是 | 设备z轴的旋转角速度，单位rad/s。 |


## GyroscopeUncalibratedResponse

未校准陀螺仪传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 设备x轴未校准的旋转角速度，单位rad/s。 |
| y | number | 是 | 是 | 设备y轴未校准的旋转角速度，单位rad/s。 |
| z | number | 是 | 是 | 设备z轴未校准的旋转角速度，单位rad/s。 |
| biasX | number | 是 | 是 | 设备x轴未校准的旋转角速度偏量，单位rad/s。 |
| biasY | number | 是 | 是 | 设备y轴未校准的旋转角速度偏量，单位rad/s。 |
| biasZ | number | 是 | 是 | 设备z轴未校准的旋转角速度偏量，单位rad/s。 |


## SignificantMotionResponse

有效运动传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| scalar | number | 是 | 是 | 表示剧烈运动程度。测量三个物理轴（x、y&nbsp;和&nbsp;z）上，设备是否存在大幅度运动；如果取值为1则代表存在大幅度运动，取值为0则代表没有大幅度运动。 |


## ProximityResponse

接近光传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| distance | number | 是 | 是 | 可见物体与设备显示器的接近程度。0表示接近，1表示远离。 |


## LightResponse

环境光传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| intensity | number | 是 | 是 | 光强（单位：勒克斯）。 |


## HallResponse

霍尔传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| status | number | 是 | 是 | 显示霍尔状态。测量设备周围是否存在磁力吸引，0表示有，1表示没有。 |


## MagneticFieldResponse

磁场传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | x轴环境磁场强度，单位 : μT。 |
| y | number | 是 | 是 | y轴环境磁场强度，单位 : μT。 |
| z | number | 是 | 是 | z轴环境磁场强度，单位 : μT。。 |


## MagneticFieldUncalibratedResponse

未校准磁场传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | x轴未校准环境磁场强度，单位 : μT。 |
| y | number | 是 | 是 | y轴未校准环境磁场强度，单位 : μT。 |
| z | number | 是 | 是 | z轴未校准环境磁场强度，单位 : μT。 |
| biasX | number | 是 | 是 | x轴未校准环境磁场强度偏量，单位 : μT。 |
| biasY | number | 是 | 是 | y轴未校准环境磁场强度偏量，单位 : μT。 |
| biasZ | number | 是 | 是 | z轴未校准环境磁场强度偏量，单位 : μT。 |


## PedometerResponse

计步传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| steps | number | 是 | 是 | 用户的行走步数。 |


## HumidityResponse

湿度传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| humidity | number | 是 | 是 | 湿度值。测量环境的相对湿度，以百分比&nbsp;(%)&nbsp;表示。 |


## PedometerDetectResponse

计步检测传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| scalar | number | 是 | 是 | 计步器检测。检测用户的计步动作，如果取值为1则代表用户产生了计步行走的动作，取值为0则代表用户没有发生运动。 |


## AmbientTemperatureResponse

温度传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| temperature | number | 是 | 是 | 环境温度（单位：摄氏度）。 |


## BarometerResponse

气压计传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| pressure | number | 是 | 是 | 压力值（单位：帕斯卡）。 |


## HeartRateResponse

心率传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| heartRate | number | 是 | 是 | 心率值。测量用户的心率数值，单位：bpm。 |


## WearDetectionResponse

佩戴检测传感器数据，继承于[Response](#response)。


| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| value | number | 是 | 是 | 表示设备是否被穿戴（1表示已穿戴，0表示未穿戴）。 |


## Options

设置传感器上报频率。

| 名称 | 参数类型 | 说明 |
| -------- | -------- | -------- |
| interval | number | 表示传感器的上报频率，默认值为200000000ns。 |


## GeomagneticResponse

设置地磁响应对象，继承于[Response](#response)。

| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| x | number | 是 | 是 | 地磁场的北分量。 |
| y | number | 是 | 是 | 地磁场的东分量。 |
| z | number | 是 | 是 | 地磁场的垂直分量。 |
| geomagneticDip | number | 是 | 是 | 地磁倾角，即地球磁场线与水平面的夹角。 |
| deflectionAngle | number | 是 | 是 | 地磁偏角，即地磁北方向与正北方向在水平面上的角度。 |
| levelIntensity | number | 是 | 是 | 地磁场的水平强度。 |
| totalIntensity | number | 是 | 是 | 地磁场的总强度。 |


## LocationOptions

| 名称 | 参数类型 | 可读 | 可写 | 说明 |
| -------- | -------- | -------- | -------- | -------- |
| latitude | number | 是 | 是 | 纬度。 |
| longitude | number | 是 | 是 | 经度。 |
| altitude | number | 是 | 是 | 海拔高度。 |