---
editable: false
sourcePath: en/_api-ref-grpc/serverless/containers/v1/containers/api-ref/grpc/Container/listOperations.md
---

# Serverless Containers Service, gRPC: ContainerService.ListOperations {#ListOperations}

Lists operations for the specified container.

## gRPC request

**rpc ListOperations ([ListContainerOperationsRequest](#yandex.cloud.serverless.containers.v1.ListContainerOperationsRequest)) returns ([ListContainerOperationsResponse](#yandex.cloud.serverless.containers.v1.ListContainerOperationsResponse))**

## ListContainerOperationsRequest {#yandex.cloud.serverless.containers.v1.ListContainerOperationsRequest}

```json
{
  "containerId": "string",
  "pageSize": "int64",
  "pageToken": "string",
  "filter": "string"
}
```

#|
||Field | Description ||
|| containerId | **string**

Required field. ID of the container to list operations for. ||
|| pageSize | **int64**

The maximum number of results per page that should be returned. If the number of available
results is larger than `pageSize`, the service returns a [ListContainerOperationsResponse.nextPageToken](#yandex.cloud.serverless.containers.v1.ListContainerOperationsResponse)
that can be used to get the next page of results in subsequent list requests.

Default value: 100. ||
|| pageToken | **string**

Page token. To get the next page of results, set `pageToken` to the
[ListContainerOperationsResponse.nextPageToken](#yandex.cloud.serverless.containers.v1.ListContainerOperationsResponse) returned by a previous list request. ||
|| filter | **string**

A filter expression that filters resources listed in the response.

The expression must specify:
1. The field name. Currently filtering can be applied to the [operation.Operation.done](#yandex.cloud.operation.Operation), [operation.Operation.createdBy](#yandex.cloud.operation.Operation) field.
2. An `=` operator.
3. The value in double quotes (`"`). Must be 3-63 characters long and match the regular expression `[a-z][-a-z0-9]{1,61}[a-z0-9]`.
Examples of a filter: `done=false`, `created_by='John.Doe'`. ||
|#

## ListContainerOperationsResponse {#yandex.cloud.serverless.containers.v1.ListContainerOperationsResponse}

```json
{
  "operations": [
    {
      "id": "string",
      "description": "string",
      "createdAt": "google.protobuf.Timestamp",
      "createdBy": "string",
      "modifiedAt": "google.protobuf.Timestamp",
      "done": "bool",
      "metadata": "google.protobuf.Any",
      // Includes only one of the fields `error`, `response`
      "error": "google.rpc.Status",
      "response": "google.protobuf.Any"
      // end of the list of possible fields
    }
  ],
  "nextPageToken": "string"
}
```

#|
||Field | Description ||
|| operations[] | **[Operation](#yandex.cloud.operation.Operation)**

List of operations for the specified container. ||
|| nextPageToken | **string**

Token for getting the next page of the list. If the number of results is greater than
the specified [ListContainerOperationsRequest.pageSize](#yandex.cloud.serverless.containers.v1.ListContainerOperationsRequest), use `nextPageToken` as the value
for the [ListContainerOperationsRequest.pageToken](#yandex.cloud.serverless.containers.v1.ListContainerOperationsRequest) parameter in the next list request.

Each subsequent page will have its own `nextPageToken` to continue paging through the results. ||
|#

## Operation {#yandex.cloud.operation.Operation}

An Operation resource. For more information, see [Operation](/docs/api-design-guide/concepts/operation).

#|
||Field | Description ||
|| id | **string**

ID of the operation. ||
|| description | **string**

Description of the operation. 0-256 characters long. ||
|| createdAt | **[google.protobuf.Timestamp](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#timestamp)**

Creation timestamp. ||
|| createdBy | **string**

ID of the user or service account who initiated the operation. ||
|| modifiedAt | **[google.protobuf.Timestamp](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#timestamp)**

The time when the Operation resource was last modified. ||
|| done | **bool**

If the value is `false`, it means the operation is still in progress.
If `true`, the operation is completed, and either `error` or `response` is available. ||
|| metadata | **[google.protobuf.Any](https://developers.google.com/protocol-buffers/docs/proto3#any)**

Service-specific metadata associated with the operation.
It typically contains the ID of the target resource that the operation is performed on.
Any method that returns a long-running operation should document the metadata type, if any. ||
|| error | **[google.rpc.Status](https://cloud.google.com/tasks/docs/reference/rpc/google.rpc#status)**

The error result of the operation in case of failure or cancellation.

Includes only one of the fields `error`, `response`.

The operation result.
If `done == false` and there was no failure detected, neither `error` nor `response` is set.
If `done == false` and there was a failure detected, `error` is set.
If `done == true`, exactly one of `error` or `response` is set. ||
|| response | **[google.protobuf.Any](https://developers.google.com/protocol-buffers/docs/proto3#any)**

The normal response of the operation in case of success.
If the original method returns no data on success, such as Delete,
the response is [google.protobuf.Empty](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Empty).
If the original method is the standard Create/Update,
the response should be the target resource of the operation.
Any method that returns a long-running operation should document the response type, if any.

Includes only one of the fields `error`, `response`.

The operation result.
If `done == false` and there was no failure detected, neither `error` nor `response` is set.
If `done == false` and there was a failure detected, `error` is set.
If `done == true`, exactly one of `error` or `response` is set. ||
|#