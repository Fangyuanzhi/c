# NetworkingV1beta1API

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**NetworkingV1beta1API_createNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_createNamespacedIngress) | **POST** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses | 
[**NetworkingV1beta1API_deleteCollectionNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_deleteCollectionNamespacedIngress) | **DELETE** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses | 
[**NetworkingV1beta1API_deleteNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_deleteNamespacedIngress) | **DELETE** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} | 
[**NetworkingV1beta1API_getAPIResources**](NetworkingV1beta1API.md#NetworkingV1beta1API_getAPIResources) | **GET** /apis/networking.k8s.io/v1beta1/ | 
[**NetworkingV1beta1API_listIngressForAllNamespaces**](NetworkingV1beta1API.md#NetworkingV1beta1API_listIngressForAllNamespaces) | **GET** /apis/networking.k8s.io/v1beta1/ingresses | 
[**NetworkingV1beta1API_listNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_listNamespacedIngress) | **GET** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses | 
[**NetworkingV1beta1API_patchNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_patchNamespacedIngress) | **PATCH** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} | 
[**NetworkingV1beta1API_patchNamespacedIngressStatus**](NetworkingV1beta1API.md#NetworkingV1beta1API_patchNamespacedIngressStatus) | **PATCH** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status | 
[**NetworkingV1beta1API_readNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_readNamespacedIngress) | **GET** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} | 
[**NetworkingV1beta1API_readNamespacedIngressStatus**](NetworkingV1beta1API.md#NetworkingV1beta1API_readNamespacedIngressStatus) | **GET** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status | 
[**NetworkingV1beta1API_replaceNamespacedIngress**](NetworkingV1beta1API.md#NetworkingV1beta1API_replaceNamespacedIngress) | **PUT** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} | 
[**NetworkingV1beta1API_replaceNamespacedIngressStatus**](NetworkingV1beta1API.md#NetworkingV1beta1API_replaceNamespacedIngressStatus) | **PUT** /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status | 


# **NetworkingV1beta1API_createNamespacedIngress**
```c
// create an Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_createNamespacedIngress(apiClient_t *apiClient, char * _namespace, networking_v1beta1_ingress_t * body, char * pretty, char * dryRun, char * fieldManager);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**body** | **[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) \*** |  | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldManager** | **char \*** | fieldManager is a name associated with the actor or entity that is making these changes. The value must be less than or 128 characters long, and only contain printable characters, as defined by https://golang.org/pkg/unicode/#IsPrint. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_deleteCollectionNamespacedIngress**
```c
// delete collection of Ingress
//
v1_status_t* NetworkingV1beta1API_deleteCollectionNamespacedIngress(apiClient_t *apiClient, char * _namespace, char * pretty, char * _continue, char * dryRun, char * fieldSelector, int gracePeriodSeconds, char * labelSelector, int limit, int orphanDependents, char * propagationPolicy, char * resourceVersion, int timeoutSeconds, v1_delete_options_t * body);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**_continue** | **char \*** | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldSelector** | **char \*** | A selector to restrict the list of returned objects by their fields. Defaults to everything. | [optional] 
**gracePeriodSeconds** | **int** | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. | [optional] 
**labelSelector** | **char \*** | A selector to restrict the list of returned objects by their labels. Defaults to everything. | [optional] 
**limit** | **int** | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional] 
**orphanDependents** | **int** | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \&quot;orphan\&quot; finalizer will be added to/removed from the object&#39;s finalizers list. Either this field or PropagationPolicy may be set, but not both. | [optional] 
**propagationPolicy** | **char \*** | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: &#39;Orphan&#39; - orphan the dependents; &#39;Background&#39; - allow the garbage collector to delete the dependents in the background; &#39;Foreground&#39; - a cascading policy that deletes all dependents in the foreground. | [optional] 
**resourceVersion** | **char \*** | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it&#39;s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. | [optional] 
**timeoutSeconds** | **int** | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. | [optional] 
**body** | **[v1_delete_options_t](v1_delete_options.md) \*** |  | [optional] 

### Return type

[v1_status_t](v1_status.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_deleteNamespacedIngress**
```c
// delete an Ingress
//
v1_status_t* NetworkingV1beta1API_deleteNamespacedIngress(apiClient_t *apiClient, char * name, char * _namespace, char * pretty, char * dryRun, int gracePeriodSeconds, int orphanDependents, char * propagationPolicy, v1_delete_options_t * body);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**gracePeriodSeconds** | **int** | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. | [optional] 
**orphanDependents** | **int** | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \&quot;orphan\&quot; finalizer will be added to/removed from the object&#39;s finalizers list. Either this field or PropagationPolicy may be set, but not both. | [optional] 
**propagationPolicy** | **char \*** | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: &#39;Orphan&#39; - orphan the dependents; &#39;Background&#39; - allow the garbage collector to delete the dependents in the background; &#39;Foreground&#39; - a cascading policy that deletes all dependents in the foreground. | [optional] 
**body** | **[v1_delete_options_t](v1_delete_options.md) \*** |  | [optional] 

### Return type

[v1_status_t](v1_status.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_getAPIResources**
```c
// get available resources
//
v1_api_resource_list_t* NetworkingV1beta1API_getAPIResources(apiClient_t *apiClient);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 

### Return type

[v1_api_resource_list_t](v1_api_resource_list.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_listIngressForAllNamespaces**
```c
// list or watch objects of kind Ingress
//
networking_v1beta1_ingress_list_t* NetworkingV1beta1API_listIngressForAllNamespaces(apiClient_t *apiClient, int allowWatchBookmarks, char * _continue, char * fieldSelector, char * labelSelector, int limit, char * pretty, char * resourceVersion, int timeoutSeconds, int watch);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**allowWatchBookmarks** | **int** | allowWatchBookmarks requests watch events with type \&quot;BOOKMARK\&quot;. Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server&#39;s discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. If the feature gate WatchBookmarks is not enabled in apiserver, this field is ignored. | [optional] 
**_continue** | **char \*** | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional] 
**fieldSelector** | **char \*** | A selector to restrict the list of returned objects by their fields. Defaults to everything. | [optional] 
**labelSelector** | **char \*** | A selector to restrict the list of returned objects by their labels. Defaults to everything. | [optional] 
**limit** | **int** | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional] 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**resourceVersion** | **char \*** | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it&#39;s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. | [optional] 
**timeoutSeconds** | **int** | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. | [optional] 
**watch** | **int** | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. | [optional] 

### Return type

[networking_v1beta1_ingress_list_t](networking_v1beta1_ingress_list.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf, application/json;stream=watch, application/vnd.kubernetes.protobuf;stream=watch

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_listNamespacedIngress**
```c
// list or watch objects of kind Ingress
//
networking_v1beta1_ingress_list_t* NetworkingV1beta1API_listNamespacedIngress(apiClient_t *apiClient, char * _namespace, char * pretty, int allowWatchBookmarks, char * _continue, char * fieldSelector, char * labelSelector, int limit, char * resourceVersion, int timeoutSeconds, int watch);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**allowWatchBookmarks** | **int** | allowWatchBookmarks requests watch events with type \&quot;BOOKMARK\&quot;. Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server&#39;s discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. If the feature gate WatchBookmarks is not enabled in apiserver, this field is ignored. | [optional] 
**_continue** | **char \*** | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional] 
**fieldSelector** | **char \*** | A selector to restrict the list of returned objects by their fields. Defaults to everything. | [optional] 
**labelSelector** | **char \*** | A selector to restrict the list of returned objects by their labels. Defaults to everything. | [optional] 
**limit** | **int** | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional] 
**resourceVersion** | **char \*** | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it&#39;s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. | [optional] 
**timeoutSeconds** | **int** | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. | [optional] 
**watch** | **int** | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. | [optional] 

### Return type

[networking_v1beta1_ingress_list_t](networking_v1beta1_ingress_list.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf, application/json;stream=watch, application/vnd.kubernetes.protobuf;stream=watch

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_patchNamespacedIngress**
```c
// partially update the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_patchNamespacedIngress(apiClient_t *apiClient, char * name, char * _namespace, object_t * body, char * pretty, char * dryRun, char * fieldManager, int force);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**body** | **[object_t](object.md) \*** |  | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldManager** | **char \*** | fieldManager is a name associated with the actor or entity that is making these changes. The value must be less than or 128 characters long, and only contain printable characters, as defined by https://golang.org/pkg/unicode/#IsPrint. This field is required for apply requests (application/apply-patch) but optional for non-apply patch types (JsonPatch, MergePatch, StrategicMergePatch). | [optional] 
**force** | **int** | Force is going to \&quot;force\&quot; Apply requests. It means user will re-acquire conflicting fields owned by other people. Force flag must be unset for non-apply patch requests. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: application/json-patch+json, application/merge-patch+json, application/strategic-merge-patch+json, application/apply-patch+yaml
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_patchNamespacedIngressStatus**
```c
// partially update status of the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_patchNamespacedIngressStatus(apiClient_t *apiClient, char * name, char * _namespace, object_t * body, char * pretty, char * dryRun, char * fieldManager, int force);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**body** | **[object_t](object.md) \*** |  | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldManager** | **char \*** | fieldManager is a name associated with the actor or entity that is making these changes. The value must be less than or 128 characters long, and only contain printable characters, as defined by https://golang.org/pkg/unicode/#IsPrint. This field is required for apply requests (application/apply-patch) but optional for non-apply patch types (JsonPatch, MergePatch, StrategicMergePatch). | [optional] 
**force** | **int** | Force is going to \&quot;force\&quot; Apply requests. It means user will re-acquire conflicting fields owned by other people. Force flag must be unset for non-apply patch requests. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: application/json-patch+json, application/merge-patch+json, application/strategic-merge-patch+json, application/apply-patch+yaml
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_readNamespacedIngress**
```c
// read the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_readNamespacedIngress(apiClient_t *apiClient, char * name, char * _namespace, char * pretty, int exact, int _export);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**exact** | **int** | Should the export be exact.  Exact export maintains cluster-specific fields like &#39;Namespace&#39;. Deprecated. Planned for removal in 1.18. | [optional] 
**_export** | **int** | Should this value be exported.  Export strips fields that a user can not specify. Deprecated. Planned for removal in 1.18. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_readNamespacedIngressStatus**
```c
// read status of the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_readNamespacedIngressStatus(apiClient_t *apiClient, char * name, char * _namespace, char * pretty);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_replaceNamespacedIngress**
```c
// replace the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_replaceNamespacedIngress(apiClient_t *apiClient, char * name, char * _namespace, networking_v1beta1_ingress_t * body, char * pretty, char * dryRun, char * fieldManager);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**body** | **[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) \*** |  | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldManager** | **char \*** | fieldManager is a name associated with the actor or entity that is making these changes. The value must be less than or 128 characters long, and only contain printable characters, as defined by https://golang.org/pkg/unicode/#IsPrint. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **NetworkingV1beta1API_replaceNamespacedIngressStatus**
```c
// replace status of the specified Ingress
//
networking_v1beta1_ingress_t* NetworkingV1beta1API_replaceNamespacedIngressStatus(apiClient_t *apiClient, char * name, char * _namespace, networking_v1beta1_ingress_t * body, char * pretty, char * dryRun, char * fieldManager);
```

### Parameters
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**apiClient** | **apiClient_t \*** | context containing the client configuration | 
**name** | **char \*** | name of the Ingress | 
**_namespace** | **char \*** | object name and auth scope, such as for teams and projects | 
**body** | **[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) \*** |  | 
**pretty** | **char \*** | If &#39;true&#39;, then the output is pretty printed. | [optional] 
**dryRun** | **char \*** | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed | [optional] 
**fieldManager** | **char \*** | fieldManager is a name associated with the actor or entity that is making these changes. The value must be less than or 128 characters long, and only contain printable characters, as defined by https://golang.org/pkg/unicode/#IsPrint. | [optional] 

### Return type

[networking_v1beta1_ingress_t](networking_v1beta1_ingress.md) *


### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

