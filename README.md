# AWS Signing utils

Utility methods for generating AWS Signature Version 4 URLs. Works fine with react-native!

Usage:

```
import { getSignedUrl } from 'aws-signing-utils';
import AWSConfig from './my-aws-config.json';

// Connecting to IoT
const clientUrl = getSignedUrl({
  method: 'GET',
  protocol: 'wss',
  canonicalUri: '/mqtt',
  service: 'iotdevicegateway',
  region: AWSConfig.region,
  secretKey: AWSConfig.secretKey,
  accessKey: AWSConfig.accessKey,
  sessionKey: AWSConfig.sessionKey,
  host: AWSConfig.iotEndpoint,
});

new Paho.MQTT.Client(clientUrl, AWSConfig.mqttTopic);
```