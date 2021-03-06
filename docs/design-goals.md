# azuredisk CSI driver design goals
### azuredisk CSI driver should be implemented as compatitable as possible with built-in [azuredisk](https://kubernetes.io/docs/concepts/storage/volumes/#azuredisk) plugin, it has following goals:

Goal | Status | Notes
--- | --- | --- |
Support service principal and msi authentication | Completed |  |
Support both Linux & Windows | In Progress | Windows related work is in progress: [Enable CSI hostpath example on windows](https://github.com/kubernetes-csi/drivers/issues/79) |
Compatible with original storage class parameters and usage| Completed | There is a little difference in static provision, see [example](https://github.com/andyzhangx/azuredisk-csi-driver/blob/master/README.md#example2-azuredisk-static-provisioninguse-an-existing-azure-file-share) |
Support sovereign cloud| Completed |  |
Support volume size grow| to-do |  |
Support snapshot | to-do |  |

### Implementation details
To prevent possible regression issues, azuredisk CSI driver use [azure cloud provider](https://github.com/kubernetes/kubernetes/tree/v1.13.0/pkg/cloudprovider/providers/azure) library. Thus, all bug fixes in the built-in azure disk plugin would be incorporated into this driver.
