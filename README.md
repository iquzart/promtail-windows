# Promtail Windows


[![Build and Push Docker Image](https://github.com/iquzart/promtail-windows/actions/workflows/build-and-push.yaml/badge.svg?branch=main)](https://github.com/iquzart/promtail-windows/actions/workflows/build-and-push.yaml)
![Docker Pulls](https://img.shields.io/docker/pulls/diquzart/promtail-win?style=flat-square)
![Release](https://img.shields.io/github/v/release/iquzart/promtail-windows?style=flat-square)
[![License](https://img.shields.io/:license-mit-blue.svg?style=flat-square)](https://badges.mit-license.org)


Promtail is a log shipping agent from the Grafana Loki stack. This repository provides a Helm chart that simplifies the deployment process and allows you to configure various aspects of the Promtail deployment on Kubernetes Windows based worker node.

## Getting Started

To deploy Promtail on Windows Kubernetes nodes using the Helm chart, follow these steps:

## Windows worker node 

The container image is based on nanoserver:ltsc2022. To successfully deploy and run this container, ensure that you are running it on a Windows worker node with the operating system version 2022 (ltsc2022).

1. **Clone the Repository:**

   ```sh
   git clone https://github.com/iquzart/promtail-windows.git
   cd promtail-windows
   ```

2. **Customize Values:**

   Open the `values.yaml` file and customize the values according to your requirements. You can configure Promtail settings, resources, security, and more.

3. **Install the Helm Chart:**

   Run the following command to install the Helm chart:

   ```sh
   helm install promtail-windows ./helm/promtail-win -f values.yaml
   ```

   Replace `promtail-windows` with the desired release name.

4. **Verify the Deployment:**

   Check the deployment status and inspect the created resources:

   ```sh
   kubectl get pods
   kubectl get services
   ```

## Configuration

The `values.yaml` file allows you to customize various aspects of the Promtail deployment, including:

- Image repository, tag, and pull policy.
- Resources (CPU and memory) requests and limits.
- Service settings (type, port, etc.).
- Security and Windows user settings.
- Auto-scaling configuration.
- Node placement settings (nodeSelector, tolerations, affinity).
- Custom Promtail configuration (Loki URL, positions file).

## Contributing

Contributions to this repository are welcome! If you find issues or want to enhance the Helm chart, feel free to submit a pull request. Make sure to follow best practices and provide clear documentation for your changes.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- Promtail by [Grafana](https://grafana.com)
