# GenAI Troubleshooting Log

| Problem                                         | Solution                                                       | Worked |
|------------------------------------------------|----------------------------------------------------------------|--------|
| kind cluster NodePort not accessible            | Used port-forward instead of NodePort                          | Yes    |
| backend pods crashed (RunContainerError)        | Fixed container arguments using kubectl patch                  | Yes    |
| nginx not routing traffic                      | Updated nginx.conf with proper Kubernetes DNS names            | Yes    |
| port 8080 already in use                       | Changed to a different port (e.g., 8082)                       | Yes    |
| metrics API not available                      | Installed metrics-server and patched with --kubelet-insecure-tls | Yes    |

## Opinion on GenAI

GenAI was very useful for debugging Kubernetes issues and understanding deployment steps. It helped identify configuration problems quickly and provided practical solutions. However, some commands required manual adjustment based on the environment, so understanding the underlying concepts was still necessary.