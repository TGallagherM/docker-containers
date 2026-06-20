# docker-containers

This repository serves as the centralized, version-controlled hub for my home server container infrastructure. It is designed to be managed via **Dockge** on **TrueNAS SCALE (Electric Eel)**. By maintaining these configurations in Git, I ensure that all service deployments are reproducible, documented, and easily recoverable.

## Repository Structure

The project is organized by service, with each folder containing its own deployment definition:

* **aprsd**: Configuration for the APRS Daemon (APRS-IS server) and its administrative interface.
* **kaspersky-updater**: Configuration for a Kaspersky antivirus database update service.
* **minecraft-bedrock/**: Configuration for hosting a Minecraft Bedrock Edition server.
* **otbr-zbt2/**: Configuration for an OpenThread Border Router (OTBR) for Thread network connectivity.

Each service directory contains:
* `compose.yaml`: The Docker Compose configuration.
* `.env.example`: Template for environment variables required by the service.

## Current Hosting
* **TrueNAS SCALE** (Electric Eel).
* **Dockge** installed and configured.
* **Environment Variables**: For any service you wish to deploy, copy the `.env.example` file to `.env` within that folder and update the variables with your local system paths and credentials.
* **User ID/Group ID**: Services are intended to run as user `apps` (UID/GID 1000) for security.

## Workflow
1. **Setup**: Clone this repository to your local machine.
2. **Environment Configuration**: For any new service, copy the `.env.example` file to `.env` within that service's folder and populate the required system paths and credentials.
3. **Deployment**:
   * Open the **Dockge** web UI.
   * Create a new stack.
   * Copy the content of the `compose.yaml` file from the relevant service folder into the Dockge stack editor.
4. **Version Control**:
   * **Commit**: Save your configuration progress locally in Eclipse once a service is tested.
   * **Push**: Push verified and stable configurations to this remote repository for backup and synchronization.

## Documentation Management
* Edits are performed in the **Eclipse IDE** using the **Wild Web Developer** plugin for YAML and Markdown support.

---
*Managed for Home Infrastructure.*