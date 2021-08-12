![Ampere Computing](https://avatars2.githubusercontent.com/u/34519842?s=400&u=1d29afaac44f477cbb0226139ec83f73faefe154&v=4)

# terraform-oci-ampere-a1

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Terraform code to launch a Ampere A1 Shape on Oracle Cloud Infrastructure (OCI) Free-Tier

## Description

Terraform code to launch a Ampere A1 Shape on Oracle Cloud Infrastructure (OCI) Free-Tier

## Requirements

 * Terraform
 * Oracle Free Tier Account


## Usage

### terraform.tfvars

The easiest way to configure is to use a terraform.tfvars in the project directory.  
The following is an example of what terraform.tfvars should look like:

```
tenancy_ocid = "ocid1.tenancy.oc1..aaaaaaaabcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopq"
user_ocid = "ocid1.user.oc1..aaaaaaaasoeefdt73o7uufpibhqofukdxzujisiwdcfv6xgy7fowfx7pm5ya"
user_ocid = "ocid1.user.oc1..aaaaaaaabcdefghijklmnopqrstuvwxyz0987654321zyxwvustqrponmlkj"
# Compartment OCID is same as Tenancy OCID for Root Compartment
compartment_ocid = "ocid1.tenancy.oc1..aaaaaaaabcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopq"
fingerprint = "a1:01:b2:02:c3:03:e4:04:10:11:12:13:14:15:16:17"
```

### Oracle OCI Specifics Notes

Some helpful notes to understand what metadata is required.

* Currently this code utilizes the "ca-montreal-1" region of Oracle's cloud.
* The Availability Domain for that region is the following: "FFpD:CA-MONTREAL-1-AD-1".  i
  * This information can be found in the webui when starting to launch an instance.

* OracleLinux Image ID for Region: "ocid1.image.oc1.ca-montreal-1.aaaaaaaad6knjdtt7y55hbsr4o3ckdx2uoj7xg7xqbjrb66nf76i7ijjaeta"
  * You must supply the OS image id for the region when selecting your OS.  Each different region will have an different ID.

### Running Terraform

```
terraform init && terraform plan && terraform apply -auto-approve
```

## References

* [https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/terraformproviderconfiguration.htm](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/terraformproviderconfiguration.htm)
* [Where to Get the Tenancy's OCID and User's OCID](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#five)
* [API Key Authentication](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/terraformproviderconfiguration.htm#APIKeyAuth)
* [Instance Principal Authorization](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/terraformproviderconfiguration.htm#instancePrincipalAuth)
* [Security Token Authentication](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/terraformproviderconfiguration.htm#securityTokenAuth)
* [How to Generate an API Signing Key](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm#two)
* [Bootstrapping a VM image in Oracle Cloud Infrastructure using Cloud-Init](https://martincarstenbach.wordpress.com/2018/11/30/bootstrapping-a-vm-image-in-oracle-cloud-infrastructure-using-cloud-init/)
* [Oracle makes building applications on Ampere A1 Compute instances easy](https://blogs.oracle.com/cloud-infrastructure/post/oracle-makes-building-applications-on-ampere-a1-compute-instances-easy?source=:ow:o:p:nav:062520CloudComputeBC)
