---
subcategory: "Kms"
layout: "oci"
page_title: "OCI: oci_kms_encrypted_data"
sidebar_current: "docs-oci-datasource-kms-encrypted_data"
description: |-
  Provides details about a specific EncryptedData
---

# Data Source: oci_kms_encrypted_data
The `oci_kms_encrypted_data` data source provides details about a specific EncryptedData

Encrypts data using the given EncryptDataDetails resource. 
Plaintext included in the example request is a base64-encoded value 
of a UTF-8 string.


## Example Usage

```hcl
data "oci_kms_encrypted_data" "test_encrypted_data" {
	#Required
	crypto_endpoint = var.encrypted_data_crypto_endpoint
	key_id = oci_kms_key.test_key.id
	plaintext = var.encrypted_data_plaintext

	#Optional
	associated_data = var.encrypted_data_associated_data
}
```

## Argument Reference

The following arguments are supported:

* `associated_data` - (Optional) Information that can be used to provide an encryption context for the encrypted data. The length of the string representation of the associatedData must be fewer than 4096 characters. 
* `crypto_endpoint` - (Required) The service endpoint to perform cryptographic operations against. Cryptographic operations include 'Encrypt,' 'Decrypt,' and 'GenerateDataEncryptionKey' operations. see Vault Crypto endpoint.
* `key_id` - (Required) The OCID of the key to encrypt with.
* `plaintext` - (Required) The plaintext data to encrypt.


## Attributes Reference

The following attributes are exported:

* `ciphertext` - The encrypted data.

