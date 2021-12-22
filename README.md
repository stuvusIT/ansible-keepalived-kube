#  Keepalived

This role configures keepalived as a static pod on a kubernetes master node.

## Requirements

This role needs the host to be configured as a working kubernetes master node.


## Role Variables


| Name                         |                          Required/Default                           | Description                                                                   |
| ---------------------------- | :-----------------------------------------------------------------: | ----------------------------------------------------------------------------- |
| `keepalived_interface`       |                         :heavy_check_mark:                          | The interface on which to configure the VIP                                   |
| `keepalived_router_id`       |                          :heavy_checkmark:                          | Router id of the vrrp instance. Should be shared by all hosts in the cluster. |
| `keepalived_vip`             |                          :heavy_checkmark:                          | The virtual IP to use                                                         |
| `keepalived_password`        |                          :heavy_checkmark:                          | passwort used for authentication between vppr instances.                      |
| `keepaliced_labels`          |                      :heavy_multiplication_x:                       | Labels to be added to the pod                                                 |
| `keepalived_namespace`       |                            `kube-system`                            | The namespace of the pod                                                      |
| `keepalived_image`           |                         `bsctl/keepalived`                          | image to use for the keepalived container                                     |
| `keepalived_config_path`     |                  `/etc/keepalived/keepalived.conf`                  | path to use for `keepalived.conf`                                             |  |
| `keepalived_health_command`  | `"/usr/bin/curl -s -k https://localhost:6443/healthz -o /dev/null"` | command to use for the health check                                           |
| `keepalived_health_timeout`  |                                 `2`                                 | timeout for the health command in seconds                                     |
| `keepalived_health_interval` |                                 `5`                                 | interval to execute the health check at                                       |
| `keepalived_health_rise`     |                                 `2`                                 | number of successful health checks necessary to become healthy                |
| `keepalived_health_fall`     |                                 `3`                                 | number of failed health checks to tolerate                                    |
| `keepalived_health_user`     |                               `root`                                | user as which to run the health check                                         |
| `keepalived_advert_interval` |                                 `3`                                 | interval for advertising the own state to other keepalived instances          |


## Example

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
```


## License

This work is licensed under the [MIT License](./LICENSE).


## Author Information

- [Sven Feyerabend](SF2311) _sven.feyerabend at stuvus.uni-stuttgart.de_
