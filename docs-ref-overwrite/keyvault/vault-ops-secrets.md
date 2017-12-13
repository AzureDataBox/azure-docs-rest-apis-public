---
uid: keyvault.setsecret.setsecret
authorization: Requires the secrets/set permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The CREATE operation adds a secret to the Azure Key Vault. If the named secret already exists, Azure Key Vault creates a new version of that secret.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

In your request:

- Name the new or to be updated secret using `{secret-name}` in the request URL.

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).

---
uid: keyvault.getsecret.getsecret
authorization: Requires the secrets/get permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The GET operation is applicable to any secret stored in Azure Key Vault.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

In your request:

- Replace `{secret-name}` with the name and `{secret-version}` with the version of the secret you want to retrieve. Secret version may be excluded in which case the current version is retrieved.

Request Body - None, this is an HTTP GET operation.

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests, and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).

---
uid: keyvault.getsecrets.getsecrets
authorization: Requires the secrets/list permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The LIST operation is applicable to the entire vault, however only the base secret identifier and attributes are provided in the response. Individual secret versions are not listed in the response.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

In your request:

- Query option `maxresults={maxresults}` is optional. The value of `maxresults` must be an non-negative integer less than 25. If a value out of the range is specified, the request will fail with an Http 400 error. If this query option is not specified, the service will return up to 25 results.

Request Body - None, this is an HTTP GET operation.

You may use the `nextLink` field via an HTTP GET to retrieve the next set of results, which will include another `nextLink` field. The enumeration is completed if and only if `nextLink` is empty

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests, and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).

---
uid: keyvault.getsecretversions.getsecretversions
authorization: Requires the secrets/list permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The LIST VERSIONS operation can be applied to all versions having the same secret name in the same key vault. The full secret identifier and attributes are provided in the response.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

No values are returned for the secrets and only current versions of a secret are listed.

In your request:

- Query option `maxresults={maxresults}` is optional. The value of `maxresults` must be an non-negative integer less than 25. If a value out of the range is specified, the request will fail with an Http 400 error. If this query option is not specified, the service will return up to 25 results.

Request Body - None, this is an HTTP GET operation.

You may use the `nextLink` field via an HTTP GET to retrieve the next set of results, which will include another `nextLink` field. The enumeration is completed if and only if `nextLink` is empty.

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests, and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).

---
uid: keyvault.deletesecret.deletesecret
authorization: Requires the secrets/delete permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The DELETE operation applies to any secret stored in Azure Key Vault. DELETE cannot be applied to an individual version of a secret.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

In your request:

- Replace `{secret-name}` with the name of the secret to delete in the request URL.

Alternative method: POST with X-HTTP-METHOD header that specifies DELETE.

Request Body - None, this is an HTTP GET operation.

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests, and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).

---
uid: keyvault.updatesecret.updatesecret
authorization: Requires the secrets/set permission.
uriParameters:
    - name: api-version
      description: Use the latest service version, 2016-10-01.
summary: *content
---

The UPDATE operation changes specified attributes of an existing stored secret. Attributes that are not specified in the request are left unchanged. The value of a secret itself cannot be changed.

See [Common parameters and headers](~/docs-ref-conceptual/keyvault/common-parameters-and-headers.md) for headers and parameters that are used by all requests.

In your request:

- Replace `{secret-name}` with the name and `{secret-version}` with the version of the secret you want to update. Secret version may be excluded in which case the current version is updated.

Alternate Method: POST with X-HTTP-METHOD header that specifies PATCH.

For more information, see [About keys, secrets, and certificates](~/docs-ref-conceptual/keyvault/about-keys--secrets-and-certificates.md) and [Authentication, requests, and responses](~/docs-ref-conceptual/keyvault/authentication--requests-and-responses.md).
