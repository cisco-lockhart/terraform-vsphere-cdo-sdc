## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_vsphere"></a> [vsphere](#requirement\_vsphere) | 2.4.2 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_vsphere"></a> [vsphere](#provider\_vsphere) | 2.4.2 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [vsphere_content_library.sdc_content_library](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/resources/content_library) | resource |
| [vsphere_content_library_item.sdc_template](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/resources/content_library_item) | resource |
| [vsphere_folder.sdc_folder](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/resources/folder) | resource |
| [vsphere_virtual_machine.sdc_vm](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/resources/virtual_machine) | resource |
| [vsphere_datacenter.datacenter](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/data-sources/datacenter) | data source |
| [vsphere_datastore.datastore](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/data-sources/datastore) | data source |
| [vsphere_host.host](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/data-sources/host) | data source |
| [vsphere_network.network](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/data-sources/network) | data source |
| [vsphere_resource_pool.resource_pool](https://registry.terraform.io/providers/hashicorp/vsphere/2.4.2/docs/data-sources/resource_pool) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_allow_unverified_ssl"></a> [allow\_unverified\_ssl](#input\_allow\_unverified\_ssl) | Boolean that can be set to true to disable SSL certificate verification. This should be used with care as it could allow an attacker to intercept your authentication token. If omitted, default value is `false`. | `bool` | `false` | no |
| <a name="input_cdo_bootstrap_data"></a> [cdo\_bootstrap\_data](#input\_cdo\_bootstrap\_data) | Specify the bootstrap data required to initialize the SDC. The SDC bootstrap data can be generated using the [SDC resource](https://registry.terraform.io/providers/CiscoDevNet/cdo/latest/docs/resources/sdc) in the [CDO Terraform Provider](https://registry.terraform.io/providers/CiscoDevNet/cdo/latest), or using the CDO UI. | `string` | n/a | yes |
| <a name="input_cdo_tenant_name"></a> [cdo\_tenant\_name](#input\_cdo\_tenant\_name) | Specify the name of the CDO tenant the SDC is being created for. | `string` | n/a | yes |
| <a name="input_cdo_user_password"></a> [cdo\_user\_password](#input\_cdo\_user\_password) | Specify the password for the `cdo` user on this VM. The `cdo` user is a user with `sudo` privileges, and is the user you will use to connect to and perform operations on the VM. | `string` | n/a | yes |
| <a name="input_datacenter"></a> [datacenter](#input\_datacenter) | Specify the name of the [vSphere datacenter](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.vcenterhost.doc/GUID-7FDFBDBE-F8AC-4D00-AE5E-3F14D7472FAF.html) where the SDC should be deployed. | `string` | n/a | yes |
| <a name="input_datacenter_region"></a> [datacenter\_region](#input\_datacenter\_region) | Specify the region closest to your vSphere datacenter. Uploading the SDC OVA to your datacenter will be done from a CDO location closest to your region. Allowed values: [eu, us]. You can alternately download the SDC OVA and upload it to a region closer to you. | `string` | `"us"` | no |
| <a name="input_datastore"></a> [datastore](#input\_datastore) | Specify the name of the [vSphere datastore](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.storage.doc/GUID-5EE84941-366D-4D37-8B7B-767D08928888.html) to use for the SDC. | `string` | n/a | yes |
| <a name="input_dns_server"></a> [dns\_server](#input\_dns\_server) | Specify the DNS servers to use on this VM. Defaults to the Cisco Umbrella DNS server. | `string` | `"208.67.222.222"` | no |
| <a name="input_gateway"></a> [gateway](#input\_gateway) | Specify the gateway through which traffic from this VM should be routed. It must be possible to access the internet through this gateway. | `string` | n/a | yes |
| <a name="input_host"></a> [host](#input\_host) | Specify the name of the [vSphere host](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.resmgmt.doc/GUID-487C09CE-8BE2-4B89-BA30-0E4F7E3C66F7.html) to use for the SDC. | `string` | n/a | yes |
| <a name="input_ip_address"></a> [ip\_address](#input\_ip\_address) | Specify the IP address to be assigned to the VM. | `string` | n/a | yes |
| <a name="input_network"></a> [network](#input\_network) | Specify the name of the [vSphere network](hhttps://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.networking.doc/GUID-35B40B0B-0C13-43B2-BC85-18C9C91BE2D4.html) to use for the SDC. | `string` | n/a | yes |
| <a name="input_ntp_server"></a> [ntp\_server](#input\_ntp\_server) | Specify the NTP server to synchronize the time on this SDC. Defaults to the Ubuntu NTP server. | `string` | `"ntp.ubuntu.com"` | no |
| <a name="input_resource_pool"></a> [resource\_pool](#input\_resource\_pool) | Specify the name of the [vSphere resource pool](https://docs.vmware.com/en/VMware-vSphere/8.0/vsphere-resource-management/GUID-60077B40-66FF-4625-934A-641703ED7601.html) where the SDC should be deployed. | `string` | n/a | yes |
| <a name="input_root_user_password"></a> [root\_user\_password](#input\_root\_user\_password) | Specify the password for the `root` user on this VM. | `string` | n/a | yes |
| <a name="input_sdc_content_library_item_id"></a> [sdc\_content\_library\_item\_id](#input\_sdc\_content\_library\_item\_id) | Specify the ID of the content library item that represents the SDC OVA. By default, this module will create a content library item per usage, which can result in excessive space usage if you are deploying SDCs for multiple tenants in a single vSphere instance. If you wish to share the SDC OVA across multiple tenants, specify this value. | `string` | `null` | no |
| <a name="input_sdc_ova_location"></a> [sdc\_ova\_location](#input\_sdc\_ova\_location) | Specify the location of the OVA file that contains the SDC. You can manually download the S3 OVA to a custom location if you wish to. | `string` | `null` | no |
| <a name="input_vsphere_password"></a> [vsphere\_password](#input\_vsphere\_password) | Specify the password for vSphere API operations. | `string` | n/a | yes |
| <a name="input_vsphere_server"></a> [vsphere\_server](#input\_vsphere\_server) | Specify the vCenter Server FQDN or IP Address for vSphere API operations. | `string` | n/a | yes |
| <a name="input_vsphere_username"></a> [vsphere\_username](#input\_vsphere\_username) | Specify the username for vSphere API operations. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_sdc_content_library_id"></a> [sdc\_content\_library\_id](#output\_sdc\_content\_library\_id) | The ID of the SDC OVA content library. |
| <a name="output_sdc_content_library_item_name"></a> [sdc\_content\_library\_item\_name](#output\_sdc\_content\_library\_item\_name) | The name of the SDC OVA content library item. |
| <a name="output_sdc_ip"></a> [sdc\_ip](#output\_sdc\_ip) | The IP address of the SDC created in Terraform. |
