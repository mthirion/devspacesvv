# Demo Stop The Crazy Train - Lego Train AI app

![lego](https://www.lego.com/cdn/cs/set/assets/blt95604d8cc65e26c4/CITYtrain_Hero-XL-Desktop.png?fit=crop&format=webply&quality=80&width=1600&height=1000&dpr=1)

# Intelligent-Train

Intelligent-Train is a Python module in a larger system that employs machine learning algorithms to interpret video data from the Capture-App. The primary function of this module is to recognize specific signs that indicate the need to slow down or stop the train.

## How it works

Intelligent-Train receives video data from the Capture-App module via MQTT. This data is processed using a machine learning model specifically trained to recognize signs that signal the need to slow down or halt the train. The module then generates raw predictions based on this analysis, which are subsequently sent to the Train-CEQ-App for further processing and decision-making.

## Prerequisites

- **MQTT Broker**: Intelligent-Train uses MQTT for messaging. An MQTT broker, accessible to Intelligent-Train, must be operational. The MQTT broker's URL should be specified in the `MQTT_BROKER_URL` environment variable.

## Dependencies

Intelligent-Train has the following dependencies:

- **paho-mqtt**: A Python client library for MQTT, used for receiving video data from the Capture-App and sending raw predictions to the Train-CEQ-App.
- **TensorFlow**: An open-source platform for machine learning, used for analyzing the received video data and recognizing specific signs.

These dependencies are managed by pip and are specified in the `requirements.txt` file.

## Related Modules

Intelligent-Train is part of a larger system that includes the following modules:

- **Capture-App**: This module captures video and sends it to Intelligent-Train.
- **Train-CEQ-App**: This module processes the raw predictions made by the Intelligent-Train module, transforming them into actionable insights.
- **Train-Monitoring-App**: This module receives the CloudEvent from Train-CEQ-App via Kafka and uses this information for monitoring and visualization purposes.
- **Train-Controller**: This module receives decisions from Train-CEQ-App and controls the operation of the train accordingly.

## How to run

1. Clone the repository: `git clone https://github.com/Demo-AI-Edge-Crazy-Train/intelligent-train.git`
2. Navigate to the project directory: `cd intelligent-train`
3. Install the dependencies: `pip install -r requirements.txt`
4. Set the `MQTT_BROKER_URL` environment variable to the URL of your MQTT broker.
5. Run the application: `python src/app.py`

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.