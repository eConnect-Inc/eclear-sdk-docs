<a name='assembly'></a>
# eClearSdk

## Contents

- [IOptional](#T-eClearSdk-Common-IOptional 'eClearSdk.Common.IOptional')
  - [HasValue](#P-eClearSdk-Common-IOptional-HasValue 'eClearSdk.Common.IOptional.HasValue')
  - [Value](#P-eClearSdk-Common-IOptional-Value 'eClearSdk.Common.IOptional.Value')
- [IRpcPersonManagement](#T-eClearSdk-v1-PersonManagement-IRpcPersonManagement 'eClearSdk.v1.PersonManagement.IRpcPersonManagement')
  - [AddUpdateAsync(externalIdKey,externalIdValue,person,cancellationToken)](#M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-AddUpdateAsync-System-String,System-String,eClearSdk-v1-PersonManagement-eClearPersonItem,System-Threading-CancellationToken- 'eClearSdk.v1.PersonManagement.IRpcPersonManagement.AddUpdateAsync(System.String,System.String,eClearSdk.v1.PersonManagement.eClearPersonItem,System.Threading.CancellationToken)')
  - [ExternalIdListAsync(externalIdKey,cancellationToken)](#M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-ExternalIdListAsync-System-String,System-Threading-CancellationToken- 'eClearSdk.v1.PersonManagement.IRpcPersonManagement.ExternalIdListAsync(System.String,System.Threading.CancellationToken)')
  - [RemoveAsync(externalIdKey,externalIdValue,cancellationToken)](#M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-RemoveAsync-System-String,System-String,System-Threading-CancellationToken- 'eClearSdk.v1.PersonManagement.IRpcPersonManagement.RemoveAsync(System.String,System.String,System.Threading.CancellationToken)')
  - [SearchAsync(externalIdKey,externalIdValue,includePhoto,cancellationToken)](#M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-SearchAsync-System-String,System-String,System-Boolean,System-Threading-CancellationToken- 'eClearSdk.v1.PersonManagement.IRpcPersonManagement.SearchAsync(System.String,System.String,System.Boolean,System.Threading.CancellationToken)')
  - [UpdateStatusAsync(externalIdKey,externalIdValue,status,cancellationToken)](#M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-UpdateStatusAsync-System-String,System-String,eClearSdk-v1-PersonManagement-PersonStatus,System-Threading-CancellationToken- 'eClearSdk.v1.PersonManagement.IRpcPersonManagement.UpdateStatusAsync(System.String,System.String,eClearSdk.v1.PersonManagement.PersonStatus,System.Threading.CancellationToken)')
- [IeClearPublishSdk](#T-eClearSdk-IeClearPublishSdk 'eClearSdk.IeClearPublishSdk')
  - [FacePublishAsync(item,cancellationToken)](#M-eClearSdk-IeClearPublishSdk-FacePublishAsync-eClearSdk-v1-Face-eClearFaceItem,System-Threading-CancellationToken- 'eClearSdk.IeClearPublishSdk.FacePublishAsync(eClearSdk.v1.Face.eClearFaceItem,System.Threading.CancellationToken)')
  - [PayloadAsync\`\`1(item,routingKey,cancellationToken)](#M-eClearSdk-IeClearPublishSdk-PayloadAsync``1-``0,System-String,System-Threading-CancellationToken- 'eClearSdk.IeClearPublishSdk.PayloadAsync``1(``0,System.String,System.Threading.CancellationToken)')
- [IeClearRpcSdk](#T-eClearSdk-IeClearRpcSdk 'eClearSdk.IeClearRpcSdk')
  - [PersonManagement](#P-eClearSdk-IeClearRpcSdk-PersonManagement 'eClearSdk.IeClearRpcSdk.PersonManagement')
- [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')
  - [Publish](#P-eClearSdk-IeClearSdk-Publish 'eClearSdk.IeClearSdk.Publish')
  - [Rpc](#P-eClearSdk-IeClearSdk-Rpc 'eClearSdk.IeClearSdk.Rpc')
  - [Subscribe](#P-eClearSdk-IeClearSdk-Subscribe 'eClearSdk.IeClearSdk.Subscribe')
  - [ServerReady()](#M-eClearSdk-IeClearSdk-ServerReady 'eClearSdk.IeClearSdk.ServerReady')
- [IeClearServerSdk](#T-eClearSdk-IeClearServerSdk 'eClearSdk.IeClearServerSdk')
- [IeClearSubscribeSdk](#T-eClearSdk-IeClearSubscribeSdk 'eClearSdk.IeClearSubscribeSdk')
  - [FaceDetectedCallback(callback,customQueueName,keepQueueEvenWhenDisconnected,deleteQueueWhenNoConsumers)](#M-eClearSdk-IeClearSubscribeSdk-FaceDetectedCallback-System-Action{eClearSdk-v1-Face-eClearFaceItem},System-String,System-Boolean,System-Boolean- 'eClearSdk.IeClearSubscribeSdk.FaceDetectedCallback(System.Action{eClearSdk.v1.Face.eClearFaceItem},System.String,System.Boolean,System.Boolean)')
  - [PayloadCallback\`\`1(callback,routingKey,customQueueName,keepQueueEvenWhenDisconnected,deleteQueueWhenNoConsumers)](#M-eClearSdk-IeClearSubscribeSdk-PayloadCallback``1-System-Action{``0},System-String,System-String,System-Boolean,System-Boolean- 'eClearSdk.IeClearSubscribeSdk.PayloadCallback``1(System.Action{``0},System.String,System.String,System.Boolean,System.Boolean)')
- [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1')
  - [#ctor(value)](#M-eClearSdk-Common-Optional`1-#ctor-`0- 'eClearSdk.Common.Optional`1.#ctor(`0)')
  - [#ctor(value,hasValue)](#M-eClearSdk-Common-Optional`1-#ctor-`0,System-Boolean- 'eClearSdk.Common.Optional`1.#ctor(`0,System.Boolean)')
  - [HasValue](#P-eClearSdk-Common-Optional`1-HasValue 'eClearSdk.Common.Optional`1.HasValue')
  - [IsEmpty](#P-eClearSdk-Common-Optional`1-IsEmpty 'eClearSdk.Common.Optional`1.IsEmpty')
  - [Value](#P-eClearSdk-Common-Optional`1-Value 'eClearSdk.Common.Optional`1.Value')
  - [Empty(defaultValue)](#M-eClearSdk-Common-Optional`1-Empty-`0- 'eClearSdk.Common.Optional`1.Empty(`0)')
  - [Equals(other)](#M-eClearSdk-Common-Optional`1-Equals-eClearSdk-Common-Optional{`0}- 'eClearSdk.Common.Optional`1.Equals(eClearSdk.Common.Optional{`0})')
  - [Equals(obj)](#M-eClearSdk-Common-Optional`1-Equals-System-Object- 'eClearSdk.Common.Optional`1.Equals(System.Object)')
  - [GetHashCode()](#M-eClearSdk-Common-Optional`1-GetHashCode 'eClearSdk.Common.Optional`1.GetHashCode')
  - [ToString()](#M-eClearSdk-Common-Optional`1-ToString 'eClearSdk.Common.Optional`1.ToString')
  - [op_Equality(left,right)](#M-eClearSdk-Common-Optional`1-op_Equality-eClearSdk-Common-Optional{`0},eClearSdk-Common-Optional{`0}- 'eClearSdk.Common.Optional`1.op_Equality(eClearSdk.Common.Optional{`0},eClearSdk.Common.Optional{`0})')
  - [op_Implicit(value)](#M-eClearSdk-Common-Optional`1-op_Implicit-`0-~eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional`1.op_Implicit(`0)~eClearSdk.Common.Optional{`0}')
  - [op_Implicit()](#M-eClearSdk-Common-Optional`1-op_Implicit-eClearSdk-Common-Optional{`0}-~`0 'eClearSdk.Common.Optional`1.op_Implicit(eClearSdk.Common.Optional{`0})~`0')
  - [op_Inequality(left,right)](#M-eClearSdk-Common-Optional`1-op_Inequality-eClearSdk-Common-Optional{`0},eClearSdk-Common-Optional{`0}- 'eClearSdk.Common.Optional`1.op_Inequality(eClearSdk.Common.Optional{`0},eClearSdk.Common.Optional{`0})')
- [PersonStatus](#T-eClearSdk-v1-PersonManagement-PersonStatus 'eClearSdk.v1.PersonManagement.PersonStatus')
  - [Active](#F-eClearSdk-v1-PersonManagement-PersonStatus-Active 'eClearSdk.v1.PersonManagement.PersonStatus.Active')
  - [Disabled](#F-eClearSdk-v1-PersonManagement-PersonStatus-Disabled 'eClearSdk.v1.PersonManagement.PersonStatus.Disabled')
- [eClearDeviceItem](#T-eClearSdk-v1-Face-eClearDeviceItem 'eClearSdk.v1.Face.eClearDeviceItem')
  - [DeviceIdentifier](#P-eClearSdk-v1-Face-eClearDeviceItem-DeviceIdentifier 'eClearSdk.v1.Face.eClearDeviceItem.DeviceIdentifier')
  - [DeviceName](#P-eClearSdk-v1-Face-eClearDeviceItem-DeviceName 'eClearSdk.v1.Face.eClearDeviceItem.DeviceName')
  - [Groups](#P-eClearSdk-v1-Face-eClearDeviceItem-Groups 'eClearSdk.v1.Face.eClearDeviceItem.Groups')
  - [MacAddress](#P-eClearSdk-v1-Face-eClearDeviceItem-MacAddress 'eClearSdk.v1.Face.eClearDeviceItem.MacAddress')
  - [TimeZone](#P-eClearSdk-v1-Face-eClearDeviceItem-TimeZone 'eClearSdk.v1.Face.eClearDeviceItem.TimeZone')
- [eClearExternalIdItem](#T-eClearSdk-v1-Face-eClearExternalIdItem 'eClearSdk.v1.Face.eClearExternalIdItem')
- [eClearExternalIdItem](#T-eClearSdk-v1-PersonManagement-eClearExternalIdItem 'eClearSdk.v1.PersonManagement.eClearExternalIdItem')
  - [IdName](#P-eClearSdk-v1-Face-eClearExternalIdItem-IdName 'eClearSdk.v1.Face.eClearExternalIdItem.IdName')
  - [Value](#P-eClearSdk-v1-Face-eClearExternalIdItem-Value 'eClearSdk.v1.Face.eClearExternalIdItem.Value')
  - [Category](#P-eClearSdk-v1-PersonManagement-eClearExternalIdItem-Category 'eClearSdk.v1.PersonManagement.eClearExternalIdItem.Category')
  - [Identifier](#P-eClearSdk-v1-PersonManagement-eClearExternalIdItem-Identifier 'eClearSdk.v1.PersonManagement.eClearExternalIdItem.Identifier')
- [eClearFaceAttributesItem](#T-eClearSdk-v1-Face-eClearFaceAttributesItem 'eClearSdk.v1.Face.eClearFaceAttributesItem')
  - [PersonTemperature](#P-eClearSdk-v1-Face-eClearFaceAttributesItem-PersonTemperature 'eClearSdk.v1.Face.eClearFaceAttributesItem.PersonTemperature')
  - [PersonTemperatureHigh](#P-eClearSdk-v1-Face-eClearFaceAttributesItem-PersonTemperatureHigh 'eClearSdk.v1.Face.eClearFaceAttributesItem.PersonTemperatureHigh')
  - [ePassResult](#P-eClearSdk-v1-Face-eClearFaceAttributesItem-ePassResult 'eClearSdk.v1.Face.eClearFaceAttributesItem.ePassResult')
- [eClearFaceItem](#T-eClearSdk-v1-Face-eClearFaceItem 'eClearSdk.v1.Face.eClearFaceItem')
  - [Attributes](#P-eClearSdk-v1-Face-eClearFaceItem-Attributes 'eClearSdk.v1.Face.eClearFaceItem.Attributes')
  - [DateTimeUtc](#P-eClearSdk-v1-Face-eClearFaceItem-DateTimeUtc 'eClearSdk.v1.Face.eClearFaceItem.DateTimeUtc')
  - [Device](#P-eClearSdk-v1-Face-eClearFaceItem-Device 'eClearSdk.v1.Face.eClearFaceItem.Device')
  - [ImageFace](#P-eClearSdk-v1-Face-eClearFaceItem-ImageFace 'eClearSdk.v1.Face.eClearFaceItem.ImageFace')
  - [ImageFull](#P-eClearSdk-v1-Face-eClearFaceItem-ImageFull 'eClearSdk.v1.Face.eClearFaceItem.ImageFull')
  - [Person](#P-eClearSdk-v1-Face-eClearFaceItem-Person 'eClearSdk.v1.Face.eClearFaceItem.Person')
  - [QrData](#P-eClearSdk-v1-Face-eClearFaceItem-QrData 'eClearSdk.v1.Face.eClearFaceItem.QrData')
  - [ServerInfo](#P-eClearSdk-v1-Face-eClearFaceItem-ServerInfo 'eClearSdk.v1.Face.eClearFaceItem.ServerInfo')
- [eClearFacePhotoItem](#T-eClearSdk-v1-PersonManagement-eClearFacePhotoItem 'eClearSdk.v1.PersonManagement.eClearFacePhotoItem')
  - [ImageData](#P-eClearSdk-v1-PersonManagement-eClearFacePhotoItem-ImageData 'eClearSdk.v1.PersonManagement.eClearFacePhotoItem.ImageData')
- [eClearGetAllByExternalIdKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyRequestItem 'eClearSdk.v1.PersonManagement.Query.eClearGetAllByExternalIdKeyRequestItem')
  - [Key](#P-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyRequestItem-Key 'eClearSdk.v1.PersonManagement.Query.eClearGetAllByExternalIdKeyRequestItem.Key')
- [eClearGetAllByExternalIdKeyResponseItem](#T-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyResponseItem 'eClearSdk.v1.PersonManagement.Query.eClearGetAllByExternalIdKeyResponseItem')
  - [Values](#P-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyResponseItem-Values 'eClearSdk.v1.PersonManagement.Query.eClearGetAllByExternalIdKeyResponseItem.Values')
- [eClearGroupItem](#T-eClearSdk-v1-Face-eClearGroupItem 'eClearSdk.v1.Face.eClearGroupItem')
  - [GroupName](#P-eClearSdk-v1-Face-eClearGroupItem-GroupName 'eClearSdk.v1.Face.eClearGroupItem.GroupName')
- [eClearInternalMethodAccess](#T-eClearSdk-Extensions-eClearInternalMethodAccess 'eClearSdk.Extensions.eClearInternalMethodAccess')
  - [ServerSdk(sdk)](#M-eClearSdk-Extensions-eClearInternalMethodAccess-ServerSdk-eClearSdk-IeClearSdk- 'eClearSdk.Extensions.eClearInternalMethodAccess.ServerSdk(eClearSdk.IeClearSdk)')
- [eClearPersonInfoItem](#T-eClearSdk-v1-Face-eClearPersonInfoItem 'eClearSdk.v1.Face.eClearPersonInfoItem')
  - [Identification](#P-eClearSdk-v1-Face-eClearPersonInfoItem-Identification 'eClearSdk.v1.Face.eClearPersonInfoItem.Identification')
  - [MatchConfidence](#P-eClearSdk-v1-Face-eClearPersonInfoItem-MatchConfidence 'eClearSdk.v1.Face.eClearPersonInfoItem.MatchConfidence')
  - [Name](#P-eClearSdk-v1-Face-eClearPersonInfoItem-Name 'eClearSdk.v1.Face.eClearPersonInfoItem.Name')
  - [PersonIdentifiers](#P-eClearSdk-v1-Face-eClearPersonInfoItem-PersonIdentifiers 'eClearSdk.v1.Face.eClearPersonInfoItem.PersonIdentifiers')
  - [PersonTags](#P-eClearSdk-v1-Face-eClearPersonInfoItem-PersonTags 'eClearSdk.v1.Face.eClearPersonInfoItem.PersonTags')
- [eClearPersonItem](#T-eClearSdk-v1-PersonManagement-eClearPersonItem 'eClearSdk.v1.PersonManagement.eClearPersonItem')
  - [ExternalIds](#P-eClearSdk-v1-PersonManagement-eClearPersonItem-ExternalIds 'eClearSdk.v1.PersonManagement.eClearPersonItem.ExternalIds')
  - [Name](#P-eClearSdk-v1-PersonManagement-eClearPersonItem-Name 'eClearSdk.v1.PersonManagement.eClearPersonItem.Name')
  - [PersonStatus](#P-eClearSdk-v1-PersonManagement-eClearPersonItem-PersonStatus 'eClearSdk.v1.PersonManagement.eClearPersonItem.PersonStatus')
  - [Photograph](#P-eClearSdk-v1-PersonManagement-eClearPersonItem-Photograph 'eClearSdk.v1.PersonManagement.eClearPersonItem.Photograph')
  - [Tags](#P-eClearSdk-v1-PersonManagement-eClearPersonItem-Tags 'eClearSdk.v1.PersonManagement.eClearPersonItem.Tags')
- [eClearPersonRemoveByExternalKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyRequestItem')
  - [Key](#P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem-Key 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyRequestItem.Key')
  - [Value](#P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem-Value 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyRequestItem.Value')
- [eClearPersonRemoveByExternalKeyResponseItem](#T-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyResponseItem 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyResponseItem')
  - [Value](#P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyResponseItem-Value 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyResponseItem.Value')
- [eClearPersonTagItem](#T-eClearSdk-v1-Face-eClearPersonTagItem 'eClearSdk.v1.Face.eClearPersonTagItem')
  - [TagName](#P-eClearSdk-v1-Face-eClearPersonTagItem-TagName 'eClearSdk.v1.Face.eClearPersonTagItem.TagName')
- [eClearPersonUpdateStatusByExternalKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyRequestItem')
  - [Key](#P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Key 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyRequestItem.Key')
  - [Status](#P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Status 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyRequestItem.Status')
  - [Value](#P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Value 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyRequestItem.Value')
- [eClearPersonUpdateStatusByExternalKeyResponseItem](#T-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyResponseItem 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyResponseItem')
  - [Value](#P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyResponseItem-Value 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyResponseItem.Value')
- [eClearPersonUpsertRequestItem](#T-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertRequestItem')
  - [Key](#P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Key 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertRequestItem.Key')
  - [Person](#P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Person 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertRequestItem.Person')
  - [Value](#P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Value 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertRequestItem.Value')
- [eClearPersonUpsertResponseItem](#T-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertResponseItem 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertResponseItem')
  - [Value](#P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertResponseItem-Value 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertResponseItem.Value')
- [eClearSdkException](#T-eClearSdk-eClearSdkException 'eClearSdk.eClearSdkException')
  - [#ctor(message)](#M-eClearSdk-eClearSdkException-#ctor-System-String- 'eClearSdk.eClearSdkException.#ctor(System.String)')
- [eClearSdkFactory](#T-eClearSdk-eClearSdkFactory 'eClearSdk.eClearSdkFactory')
  - [ConnectionBuildLock](#F-eClearSdk-eClearSdkFactory-ConnectionBuildLock 'eClearSdk.eClearSdkFactory.ConnectionBuildLock')
  - [ExchangeDefaultName](#F-eClearSdk-eClearSdkFactory-ExchangeDefaultName 'eClearSdk.eClearSdkFactory.ExchangeDefaultName')
  - [BusCache](#P-eClearSdk-eClearSdkFactory-BusCache 'eClearSdk.eClearSdkFactory.BusCache')
  - [BusIdleEviction(key,value,reason,state)](#M-eClearSdk-eClearSdkFactory-BusIdleEviction-System-Object,System-Object,Microsoft-Extensions-Caching-Memory-EvictionReason,System-Object- 'eClearSdk.eClearSdkFactory.BusIdleEviction(System.Object,System.Object,Microsoft.Extensions.Caching.Memory.EvictionReason,System.Object)')
  - [GetReadySdk(creds,allowBusCleanup)](#M-eClearSdk-eClearSdkFactory-GetReadySdk-MessageBus-RabbitMqCredentials,System-Boolean- 'eClearSdk.eClearSdkFactory.GetReadySdk(MessageBus.RabbitMqCredentials,System.Boolean)')
  - [GetReadySdk(connectionString,allowBusCleanup)](#M-eClearSdk-eClearSdkFactory-GetReadySdk-System-String,System-Boolean- 'eClearSdk.eClearSdkFactory.GetReadySdk(System.String,System.Boolean)')
  - [GetReadySdk(connectionString,durable,allowBusCleanup,exchange)](#M-eClearSdk-eClearSdkFactory-GetReadySdk-System-String,System-String,System-Boolean,System-Boolean- 'eClearSdk.eClearSdkFactory.GetReadySdk(System.String,System.String,System.Boolean,System.Boolean)')
  - [GetSdkFromConnectionString(connectionString)](#M-eClearSdk-eClearSdkFactory-GetSdkFromConnectionString-System-String- 'eClearSdk.eClearSdkFactory.GetSdkFromConnectionString(System.String)')
  - [GetSdkFromRabbitMqCredentials(rabbitMqCredentials)](#M-eClearSdk-eClearSdkFactory-GetSdkFromRabbitMqCredentials-MessageBus-RabbitMqCredentials- 'eClearSdk.eClearSdkFactory.GetSdkFromRabbitMqCredentials(MessageBus.RabbitMqCredentials)')
  - [GetSdkFromYamlFile(ymlFile)](#M-eClearSdk-eClearSdkFactory-GetSdkFromYamlFile-System-String- 'eClearSdk.eClearSdkFactory.GetSdkFromYamlFile(System.String)')
  - [GetSdkFromYamlString(ymlString)](#M-eClearSdk-eClearSdkFactory-GetSdkFromYamlString-System-String- 'eClearSdk.eClearSdkFactory.GetSdkFromYamlString(System.String)')
- [eClearSdkNonDisposable](#T-eClearSdk-eClearSdkNonDisposable 'eClearSdk.eClearSdkNonDisposable')
  - [AddUsage()](#M-eClearSdk-eClearSdkNonDisposable-AddUsage 'eClearSdk.eClearSdkNonDisposable.AddUsage')
  - [Dispose()](#M-eClearSdk-eClearSdkNonDisposable-Dispose 'eClearSdk.eClearSdkNonDisposable.Dispose')
  - [Teardown()](#M-eClearSdk-eClearSdkNonDisposable-Teardown 'eClearSdk.eClearSdkNonDisposable.Teardown')
- [eClearSearchByExternalIdRequestItem](#T-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdRequestItem')
  - [IncludePhoto](#P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-IncludePhoto 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdRequestItem.IncludePhoto')
  - [Key](#P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-Key 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdRequestItem.Key')
  - [Value](#P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-Value 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdRequestItem.Value')
- [eClearSearchByExternalIdResponseItem](#T-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdResponseItem 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdResponseItem')
  - [PersonItem](#P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdResponseItem-PersonItem 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdResponseItem.PersonItem')
- [eClearServerInfoItem](#T-eClearSdk-v1-Face-eClearServerInfoItem 'eClearSdk.v1.Face.eClearServerInfoItem')
  - [SystemId](#P-eClearSdk-v1-Face-eClearServerInfoItem-SystemId 'eClearSdk.v1.Face.eClearServerInfoItem.SystemId')
  - [SystemName](#P-eClearSdk-v1-Face-eClearServerInfoItem-SystemName 'eClearSdk.v1.Face.eClearServerInfoItem.SystemName')
- [eClearTagItem](#T-eClearSdk-v1-PersonManagement-eClearTagItem 'eClearSdk.v1.PersonManagement.eClearTagItem')
  - [TagName](#P-eClearSdk-v1-PersonManagement-eClearTagItem-TagName 'eClearSdk.v1.PersonManagement.eClearTagItem.TagName')
- [ePassReportMetadata](#T-eClearSdk-v1-ePass-ePassReportMetadata 'eClearSdk.v1.ePass.ePassReportMetadata')
  - [Key](#P-eClearSdk-v1-ePass-ePassReportMetadata-Key 'eClearSdk.v1.ePass.ePassReportMetadata.Key')
  - [Value](#P-eClearSdk-v1-ePass-ePassReportMetadata-Value 'eClearSdk.v1.ePass.ePassReportMetadata.Value')
- [ePassReportResult](#T-eClearSdk-v1-Face-ePassReportResult 'eClearSdk.v1.Face.ePassReportResult')
  - [Fail](#F-eClearSdk-v1-Face-ePassReportResult-Fail 'eClearSdk.v1.Face.ePassReportResult.Fail')
  - [NoSubmission](#F-eClearSdk-v1-Face-ePassReportResult-NoSubmission 'eClearSdk.v1.Face.ePassReportResult.NoSubmission')
  - [Pass](#F-eClearSdk-v1-Face-ePassReportResult-Pass 'eClearSdk.v1.Face.ePassReportResult.Pass')
- [ePassResultItem](#T-eClearSdk-v1-ePass-ePassResultItem 'eClearSdk.v1.ePass.ePassResultItem')
  - [DateTimeUtc](#P-eClearSdk-v1-ePass-ePassResultItem-DateTimeUtc 'eClearSdk.v1.ePass.ePassResultItem.DateTimeUtc')
  - [Email](#P-eClearSdk-v1-ePass-ePassResultItem-Email 'eClearSdk.v1.ePass.ePassResultItem.Email')
  - [FirstName](#P-eClearSdk-v1-ePass-ePassResultItem-FirstName 'eClearSdk.v1.ePass.ePassResultItem.FirstName')
  - [LastName](#P-eClearSdk-v1-ePass-ePassResultItem-LastName 'eClearSdk.v1.ePass.ePassResultItem.LastName')
  - [Metadata](#P-eClearSdk-v1-ePass-ePassResultItem-Metadata 'eClearSdk.v1.ePass.ePassResultItem.Metadata')
  - [Pass](#P-eClearSdk-v1-ePass-ePassResultItem-Pass 'eClearSdk.v1.ePass.ePassResultItem.Pass')
  - [PersonId](#P-eClearSdk-v1-ePass-ePassResultItem-PersonId 'eClearSdk.v1.ePass.ePassResultItem.PersonId')
  - [ReferenceId](#P-eClearSdk-v1-ePass-ePassResultItem-ReferenceId 'eClearSdk.v1.ePass.ePassResultItem.ReferenceId')

<a name='T-eClearSdk-Common-IOptional'></a>
## IOptional `type`

##### Namespace

eClearSdk.Common

##### Summary

This interface represents a way to access optionals easier
without the need to know the actual value type.

<a name='P-eClearSdk-Common-IOptional-HasValue'></a>
### HasValue `property`

##### Summary

`true` if the optional has a value.

<a name='P-eClearSdk-Common-IOptional-Value'></a>
### Value `property`

##### Summary

The name value.

<a name='T-eClearSdk-v1-PersonManagement-IRpcPersonManagement'></a>
## IRpcPersonManagement `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

Provides RPC calls for Person Management

<a name='M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-AddUpdateAsync-System-String,System-String,eClearSdk-v1-PersonManagement-eClearPersonItem,System-Threading-CancellationToken-'></a>
### AddUpdateAsync(externalIdKey,externalIdValue,person,cancellationToken) `method`

##### Summary

Add or Update a person in the eClear person database.

##### Returns

Returns true if successfully applied.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| externalIdKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External Id Category Name such as "EmployeeId". |
| externalIdValue | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External id Category Value such as 12345 |
| person | [eClearSdk.v1.PersonManagement.eClearPersonItem](#T-eClearSdk-v1-PersonManagement-eClearPersonItem 'eClearSdk.v1.PersonManagement.eClearPersonItem') | The person add/update object |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') | Cancel Token to abort the action |

<a name='M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-ExternalIdListAsync-System-String,System-Threading-CancellationToken-'></a>
### ExternalIdListAsync(externalIdKey,cancellationToken) `method`

##### Summary

Get a list of all the values of an external id / category

##### Returns

Returns a list of ids that match the external Id Category

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| externalIdKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Category Name such as 'employee id' |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') |  |

<a name='M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-RemoveAsync-System-String,System-String,System-Threading-CancellationToken-'></a>
### RemoveAsync(externalIdKey,externalIdValue,cancellationToken) `method`

##### Summary

Remove a person from the eClear database

##### Returns

Returns true if successfully applied.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| externalIdKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External Category name such as EmployeeId |
| externalIdValue | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External Category value that matches the Key such as 12345 |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') | Cancel Token to abort the action |

<a name='M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-SearchAsync-System-String,System-String,System-Boolean,System-Threading-CancellationToken-'></a>
### SearchAsync(externalIdKey,externalIdValue,includePhoto,cancellationToken) `method`

##### Summary

Search for a person based on their External Id (such as Employee Id) and the value for the external id (such as 1234)

##### Returns

Returns a single [eClearPersonItem](#T-eClearSdk-v1-PersonManagement-eClearPersonItem 'eClearSdk.v1.PersonManagement.eClearPersonItem') objects matching the External Id Key and Value

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| externalIdKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Category Name such as 'employee id' |
| externalIdValue | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Category Value such as '1234' |
| includePhoto | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | Include binary data of face photo if available - increases payload size and time to deliver |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') |  |

<a name='M-eClearSdk-v1-PersonManagement-IRpcPersonManagement-UpdateStatusAsync-System-String,System-String,eClearSdk-v1-PersonManagement-PersonStatus,System-Threading-CancellationToken-'></a>
### UpdateStatusAsync(externalIdKey,externalIdValue,status,cancellationToken) `method`

##### Summary

Update the persons status as Active or Disabled based on their External Id / Value

##### Returns

Returns true if successfully applied.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| externalIdKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External Category name such as EmployeeId |
| externalIdValue | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | External Category value that matches the Key such as 12345 |
| status | [eClearSdk.v1.PersonManagement.PersonStatus](#T-eClearSdk-v1-PersonManagement-PersonStatus 'eClearSdk.v1.PersonManagement.PersonStatus') | The desired status of the person [PersonStatus](#T-eClearSdk-v1-PersonManagement-PersonStatus 'eClearSdk.v1.PersonManagement.PersonStatus') |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') | Cancel Token to abort the action |

<a name='T-eClearSdk-IeClearPublishSdk'></a>
## IeClearPublishSdk `type`

##### Namespace

eClearSdk

##### Summary

Publish messages without expecting an instance response

<a name='M-eClearSdk-IeClearPublishSdk-FacePublishAsync-eClearSdk-v1-Face-eClearFaceItem,System-Threading-CancellationToken-'></a>
### FacePublishAsync(item,cancellationToken) `method`

##### Summary

Publish face detections and their associated match if available

##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| item | [eClearSdk.v1.Face.eClearFaceItem](#T-eClearSdk-v1-Face-eClearFaceItem 'eClearSdk.v1.Face.eClearFaceItem') | eClear Face item |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') |  |

<a name='M-eClearSdk-IeClearPublishSdk-PayloadAsync``1-``0,System-String,System-Threading-CancellationToken-'></a>
### PayloadAsync\`\`1(item,routingKey,cancellationToken) `method`

##### Summary

Use this method to publish message to the bus that are not defined by the SDK. This
api is used for custom integrations and private messaging

##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| item | [\`\`0](#T-``0 '``0') | Object to be sent |
| routingKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Custom Routing Key |
| cancellationToken | [System.Threading.CancellationToken](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Threading.CancellationToken 'System.Threading.CancellationToken') | Cancel Token |

##### Generic Types

| Name | Description |
| ---- | ----------- |
| T | Type of object to be sent |

<a name='T-eClearSdk-IeClearRpcSdk'></a>
## IeClearRpcSdk `type`

##### Namespace

eClearSdk

##### Summary

eConnect eClear RPC calls. These functions will execute and give a result

<a name='P-eClearSdk-IeClearRpcSdk-PersonManagement'></a>
### PersonManagement `property`

##### Summary

Person management RPC interface calls [IRpcPersonManagement](#T-eClearSdk-v1-PersonManagement-IRpcPersonManagement 'eClearSdk.v1.PersonManagement.IRpcPersonManagement')

<a name='T-eClearSdk-IeClearSdk'></a>
## IeClearSdk `type`

##### Namespace

eClearSdk

##### Summary

eConnect eClear SDK with access to Publish, RPC and Server Callback hooks

<a name='P-eClearSdk-IeClearSdk-Publish'></a>
### Publish `property`

##### Summary

eClear publish out message infrastructure [IeClearPublishSdk](#T-eClearSdk-IeClearPublishSdk 'eClearSdk.IeClearPublishSdk')

<a name='P-eClearSdk-IeClearSdk-Rpc'></a>
### Rpc `property`

##### Summary

eClear RPC Infrastructure [IeClearRpcSdk](#T-eClearSdk-IeClearRpcSdk 'eClearSdk.IeClearRpcSdk')

<a name='P-eClearSdk-IeClearSdk-Subscribe'></a>
### Subscribe `property`

##### Summary

eClear data subscription services [IeClearSubscribeSdk](#T-eClearSdk-IeClearSubscribeSdk 'eClearSdk.IeClearSubscribeSdk')

<a name='M-eClearSdk-IeClearSdk-ServerReady'></a>
### ServerReady() `method`

##### Summary

Indicate that the server is ready to receive messages. This should be called
after all of the callback hooks have been applied. If this is not called
the server calls will not be bound.

##### Parameters

This method has no parameters.

<a name='T-eClearSdk-IeClearServerSdk'></a>
## IeClearServerSdk `type`

##### Namespace

eClearSdk

##### Summary

eClear SDK Callback Interfaces for data subscriptions

<a name='T-eClearSdk-IeClearSubscribeSdk'></a>
## IeClearSubscribeSdk `type`

##### Namespace

eClearSdk

##### Summary

eClear SDK Callback Interfaces for data subscriptions

<a name='M-eClearSdk-IeClearSubscribeSdk-FaceDetectedCallback-System-Action{eClearSdk-v1-Face-eClearFaceItem},System-String,System-Boolean,System-Boolean-'></a>
### FaceDetectedCallback(callback,customQueueName,keepQueueEvenWhenDisconnected,deleteQueueWhenNoConsumers) `method`

##### Summary

When a face is detected at a kiosk a callback will be generated from the bus. Use this function to
capture all messages real time.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| callback | [System.Action{eClearSdk.v1.Face.eClearFaceItem}](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Action 'System.Action{eClearSdk.v1.Face.eClearFaceItem}') | Function callback |
| customQueueName | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | If you do not want to loose any data when the software is disconnected, provide a queue name that is the same between software restarts. |
| keepQueueEvenWhenDisconnected | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | If you want this queue to be durable. Make sure to also set autoDelete param to false to prevent removal upon disconnection |
| deleteQueueWhenNoConsumers | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | When all consumers of this queue disconnect, the queue will delete. If you have a durable queue, be sure to pass false |

<a name='M-eClearSdk-IeClearSubscribeSdk-PayloadCallback``1-System-Action{``0},System-String,System-String,System-Boolean,System-Boolean-'></a>
### PayloadCallback\`\`1(callback,routingKey,customQueueName,keepQueueEvenWhenDisconnected,deleteQueueWhenNoConsumers) `method`

##### Summary

Subscribe to messages not defined by the SDK.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| callback | [System.Action{\`\`0}](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Action 'System.Action{``0}') | Callback for the type |
| routingKey | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Routing Key |
| customQueueName | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | If you do not want to loose any data when the software is disconnected, provide a queue name that is the same between software restarts. |
| keepQueueEvenWhenDisconnected | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | If you want this queue to be durable. Make sure to also set autoDelete param to false to prevent removal upon disconnection |
| deleteQueueWhenNoConsumers | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | When all consumers of this queue disconnect, the queue will delete. If you have a durable queue, be sure to pass false |

##### Generic Types

| Name | Description |
| ---- | ----------- |
| T | Type expected back |

<a name='T-eClearSdk-Common-Optional`1'></a>
## Optional\`1 `type`

##### Namespace

eClearSdk.Common

##### Summary

The optional type is used to differentiate between not set and set input values.

##### Generic Types

| Name | Description |
| ---- | ----------- |
| T | The optional data type |

<a name='M-eClearSdk-Common-Optional`1-#ctor-`0-'></a>
### #ctor(value) `constructor`

##### Summary

Initializes a new instance of the [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') struct.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| value | [\`0](#T-`0 '`0') | The actual value. |

<a name='M-eClearSdk-Common-Optional`1-#ctor-`0,System-Boolean-'></a>
### #ctor(value,hasValue) `constructor`

##### Summary

Default SerializationConstructor needed for the RPC

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| value | [\`0](#T-`0 '`0') |  |
| hasValue | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') |  |

<a name='P-eClearSdk-Common-Optional`1-HasValue'></a>
### HasValue `property`

##### Summary

`true` if the optional was explicitly set.

<a name='P-eClearSdk-Common-Optional`1-IsEmpty'></a>
### IsEmpty `property`

##### Summary

`true` if the optional was not explicitly set.

<a name='P-eClearSdk-Common-Optional`1-Value'></a>
### Value `property`

##### Summary

The name value.

<a name='M-eClearSdk-Common-Optional`1-Empty-`0-'></a>
### Empty(defaultValue) `method`

##### Summary

Creates an empty optional that provides a default value.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| defaultValue | [\`0](#T-`0 '`0') | The default value. |

<a name='M-eClearSdk-Common-Optional`1-Equals-eClearSdk-Common-Optional{`0}-'></a>
### Equals(other) `method`

##### Summary

Compares this [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') value to another value.

##### Returns

`true` if both [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') values are equal.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| other | [eClearSdk.Common.Optional{\`0}](#T-eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional{`0}') | The second [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') for comparison. |

<a name='M-eClearSdk-Common-Optional`1-Equals-System-Object-'></a>
### Equals(obj) `method`

##### Summary

Compares this [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') value to another value.

##### Returns

`true` if both [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') values are equal.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| obj | [System.Object](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Object 'System.Object') | The second [Optional\`1](#T-eClearSdk-Common-Optional`1 'eClearSdk.Common.Optional`1') for comparison. |

<a name='M-eClearSdk-Common-Optional`1-GetHashCode'></a>
### GetHashCode() `method`

##### Summary

Serves as a hash function for a object.

##### Returns

A hash code for this instance that is suitable for use in hashing
algorithms and data structures such as a hash table.

##### Parameters

This method has no parameters.

<a name='M-eClearSdk-Common-Optional`1-ToString'></a>
### ToString() `method`

##### Summary

Provides the name string.

##### Returns

The name string value

##### Parameters

This method has no parameters.

<a name='M-eClearSdk-Common-Optional`1-op_Equality-eClearSdk-Common-Optional{`0},eClearSdk-Common-Optional{`0}-'></a>
### op_Equality(left,right) `method`

##### Summary

Operator call through to Equals

##### Returns

`true` if both "Optional" values are equal.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [eClearSdk.Common.Optional{\`0}](#T-eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional{`0}') | The left parameter |
| right | [eClearSdk.Common.Optional{\`0}](#T-eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional{`0}') | The right parameter |

<a name='M-eClearSdk-Common-Optional`1-op_Implicit-`0-~eClearSdk-Common-Optional{`0}'></a>
### op_Implicit(value) `method`

##### Summary

Implicitly creates a new "Optional" from
the given value.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| value | [\`0)~eClearSdk.Common.Optional{\`0}](#T-`0-~eClearSdk-Common-Optional{`0} '`0)~eClearSdk.Common.Optional{`0}') | The value. |

<a name='M-eClearSdk-Common-Optional`1-op_Implicit-eClearSdk-Common-Optional{`0}-~`0'></a>
### op_Implicit() `method`

##### Summary

Implicitly gets the optional value.

##### Parameters

This method has no parameters.

<a name='M-eClearSdk-Common-Optional`1-op_Inequality-eClearSdk-Common-Optional{`0},eClearSdk-Common-Optional{`0}-'></a>
### op_Inequality(left,right) `method`

##### Summary

Operator call through to Equals

##### Returns

`true` if both values are not equal.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [eClearSdk.Common.Optional{\`0}](#T-eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional{`0}') | The left parameter |
| right | [eClearSdk.Common.Optional{\`0}](#T-eClearSdk-Common-Optional{`0} 'eClearSdk.Common.Optional{`0}') | The right parameter |

<a name='T-eClearSdk-v1-PersonManagement-PersonStatus'></a>
## PersonStatus `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

Information applied to the persons record if they are active people in the face database or disabled

<a name='F-eClearSdk-v1-PersonManagement-PersonStatus-Active'></a>
### Active `constants`

##### Summary

Active and enabled user in the system

<a name='F-eClearSdk-v1-PersonManagement-PersonStatus-Disabled'></a>
### Disabled `constants`

##### Summary

Disable user, don't synchronize to the device equipment.

<a name='T-eClearSdk-v1-Face-eClearDeviceItem'></a>
## eClearDeviceItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

eClear Device Information

<a name='P-eClearSdk-v1-Face-eClearDeviceItem-DeviceIdentifier'></a>
### DeviceIdentifier `property`

##### Summary

The unique identifier for this unit, representing a unique ID per device.

<a name='P-eClearSdk-v1-Face-eClearDeviceItem-DeviceName'></a>
### DeviceName `property`

##### Summary

The Friendly device name. Front Door 1, etc

<a name='P-eClearSdk-v1-Face-eClearDeviceItem-Groups'></a>
### Groups `property`

##### Summary

eClear Device groups for adding this sensor data to a collection of different groups

<a name='P-eClearSdk-v1-Face-eClearDeviceItem-MacAddress'></a>
### MacAddress `property`

##### Summary

If known, the device mat address

<a name='P-eClearSdk-v1-Face-eClearDeviceItem-TimeZone'></a>
### TimeZone `property`

##### Summary

The IANA timezone of the device

<a name='T-eClearSdk-v1-Face-eClearExternalIdItem'></a>
## eClearExternalIdItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

The External ID is for outside systems that reference information such as an Employee ID, or Patron ID.

<a name='T-eClearSdk-v1-PersonManagement-eClearExternalIdItem'></a>
## eClearExternalIdItem `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

External Id Container - Employee or Patron information

<a name='P-eClearSdk-v1-Face-eClearExternalIdItem-IdName'></a>
### IdName `property`

##### Summary

The Type of ID. This key must be available in the eClear system.  Once defined, pass that string
so we know what it is. You can have several different kinds of IDs such as EmployeeId, PatronId, etc.
Please login to eClear to find out what keys are available or query with the Rpc call

<a name='P-eClearSdk-v1-Face-eClearExternalIdItem-Value'></a>
### Value `property`

##### Summary

The value connected to the Id type.

<a name='P-eClearSdk-v1-PersonManagement-eClearExternalIdItem-Category'></a>
### Category `property`

##### Summary

The type of Key such as EmployeeId

<a name='P-eClearSdk-v1-PersonManagement-eClearExternalIdItem-Identifier'></a>
### Identifier `property`

##### Summary

The Associated identifier tied to the Category

<a name='T-eClearSdk-v1-Face-eClearFaceAttributesItem'></a>
## eClearFaceAttributesItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

Specific detection algorithms for different attributes or other metrics provided by the device

<a name='P-eClearSdk-v1-Face-eClearFaceAttributesItem-PersonTemperature'></a>
### PersonTemperature `property`

##### Summary

If the device supports thermal readings of the subject in front of it, the value will be supplied. This value
does not specify fahrenheit or celsius, so a ranged based decision will need to be made to determine that value

<a name='P-eClearSdk-v1-Face-eClearFaceAttributesItem-PersonTemperatureHigh'></a>
### PersonTemperatureHigh `property`

##### Summary

When the device reports that the face temp was high, we will also indicate that with this flag
The device has a configured threshold where it will say it, so we honor the device flag

<a name='P-eClearSdk-v1-Face-eClearFaceAttributesItem-ePassResult'></a>
### ePassResult `property`

##### Summary

If ePass is implemented, the ePass result will be included here.
null = Not enabled
0 = No report found
1 = Pass report
2 = Fail Report

<a name='T-eClearSdk-v1-Face-eClearFaceItem'></a>
## eClearFaceItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

Container class for faces that are detected with the eClear service

<a name='P-eClearSdk-v1-Face-eClearFaceItem-Attributes'></a>
### Attributes `property`

##### Summary

Face Attributes, even if the face was not matched

<a name='P-eClearSdk-v1-Face-eClearFaceItem-DateTimeUtc'></a>
### DateTimeUtc `property`

##### Summary

The Utc timestamp of the event

<a name='P-eClearSdk-v1-Face-eClearFaceItem-Device'></a>
### Device `property`

##### Summary

The device specific information where the event originated from

<a name='P-eClearSdk-v1-Face-eClearFaceItem-ImageFace'></a>
### ImageFace `property`

##### Summary

The face image bytes associated with this request

<a name='P-eClearSdk-v1-Face-eClearFaceItem-ImageFull'></a>
### ImageFull `property`

##### Summary

The entire image port, not just the cropped face image

<a name='P-eClearSdk-v1-Face-eClearFaceItem-Person'></a>
### Person `property`

##### Summary

If the face matches to a person, the person information will be supplied

<a name='P-eClearSdk-v1-Face-eClearFaceItem-QrData'></a>
### QrData `property`

##### Summary

If Qr Code detection is enabled, a detection will find all QR/Barcode data and pass
it in this array.

<a name='P-eClearSdk-v1-Face-eClearFaceItem-ServerInfo'></a>
### ServerInfo `property`

##### Summary

Server information where the data originated from

<a name='T-eClearSdk-v1-PersonManagement-eClearFacePhotoItem'></a>
## eClearFacePhotoItem `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

Photo Container that ties the photo to the individuals record

<a name='P-eClearSdk-v1-PersonManagement-eClearFacePhotoItem-ImageData'></a>
### ImageData `property`

##### Summary

Image Data (Jpeg byte array desired)

<a name='T-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyRequestItem'></a>
## eClearGetAllByExternalIdKeyRequestItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Query

##### Summary

Request container for getting all external ids associated to a external id name.
Can be used to find if a user is already added to the database by ID

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyRequestItem-Key'></a>
### Key `property`

##### Summary

The external Id value

<a name='T-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyResponseItem'></a>
## eClearGetAllByExternalIdKeyResponseItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Query

##### Summary

Response Item to the [eClearGetAllByExternalIdKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyRequestItem 'eClearSdk.v1.PersonManagement.Query.eClearGetAllByExternalIdKeyRequestItem')

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearGetAllByExternalIdKeyResponseItem-Values'></a>
### Values `property`

##### Summary

List of available IDs associated to the requested type

<a name='T-eClearSdk-v1-Face-eClearGroupItem'></a>
## eClearGroupItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

A single group container

<a name='P-eClearSdk-v1-Face-eClearGroupItem-GroupName'></a>
### GroupName `property`

##### Summary

Name of the group

<a name='T-eClearSdk-Extensions-eClearInternalMethodAccess'></a>
## eClearInternalMethodAccess `type`

##### Namespace

eClearSdk.Extensions

<a name='M-eClearSdk-Extensions-eClearInternalMethodAccess-ServerSdk-eClearSdk-IeClearSdk-'></a>
### ServerSdk(sdk) `method`

##### Summary

Gets the eConnect Sdk Instance for hosting RPC calls from the eClear service

##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| sdk | [eClearSdk.IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk') |  |

<a name='T-eClearSdk-v1-Face-eClearPersonInfoItem'></a>
## eClearPersonInfoItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

eClear Person Detected Information

<a name='P-eClearSdk-v1-Face-eClearPersonInfoItem-Identification'></a>
### Identification `property`

##### Summary

ID of person detected - this ID is defined by the application usage

<a name='P-eClearSdk-v1-Face-eClearPersonInfoItem-MatchConfidence'></a>
### MatchConfidence `property`

##### Summary

Match Confidence to the enrolled photo

<a name='P-eClearSdk-v1-Face-eClearPersonInfoItem-Name'></a>
### Name `property`

##### Summary

Name of person detected

<a name='P-eClearSdk-v1-Face-eClearPersonInfoItem-PersonIdentifiers'></a>
### PersonIdentifiers `property`

##### Summary

If the face database has external identifiers such as HR IDs, payroll system IDs, etc, they
will be included

<a name='P-eClearSdk-v1-Face-eClearPersonInfoItem-PersonTags'></a>
### PersonTags `property`

##### Summary

If tags are associated to this person, the tag objects will be supplied here.

<a name='T-eClearSdk-v1-PersonManagement-eClearPersonItem'></a>
## eClearPersonItem `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

eClear person record, allowing the API to update a person in the eClear face database.

<a name='P-eClearSdk-v1-PersonManagement-eClearPersonItem-ExternalIds'></a>
### ExternalIds `property`

##### Summary

Optionally update / add External Ids to a person. If not supplied, this value will leave server configurations alone

<a name='P-eClearSdk-v1-PersonManagement-eClearPersonItem-Name'></a>
### Name `property`

##### Summary

Optionally update the Name of a person - if not set, this value will not be updated

<a name='P-eClearSdk-v1-PersonManagement-eClearPersonItem-PersonStatus'></a>
### PersonStatus `property`

##### Summary

The Person Status - this will be used to enable or disable a user from synchronization to the equipment.

<a name='P-eClearSdk-v1-PersonManagement-eClearPersonItem-Photograph'></a>
### Photograph `property`

##### Summary

Provide an optional photograph of the person. This can also update the photo for a person

<a name='P-eClearSdk-v1-PersonManagement-eClearPersonItem-Tags'></a>
### Tags `property`

##### Summary

The Associated eClear Tags tied to this user. If not supplied, the default value will be left alone on the server

<a name='T-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem'></a>
## eClearPersonRemoveByExternalKeyRequestItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Remove

##### Summary

eClear Person Remove by External Id

<a name='P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem-Key'></a>
### Key `property`

##### Summary

The External Id Key Category Name

<a name='P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem-Value'></a>
### Value `property`

##### Summary

The value associated to the Category Name

<a name='T-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyResponseItem'></a>
## eClearPersonRemoveByExternalKeyResponseItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Remove

##### Summary

The Response to the request [eClearPersonRemoveByExternalKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyRequestItem 'eClearSdk.v1.PersonManagement.Remove.eClearPersonRemoveByExternalKeyRequestItem')

<a name='P-eClearSdk-v1-PersonManagement-Remove-eClearPersonRemoveByExternalKeyResponseItem-Value'></a>
### Value `property`

##### Summary

If a successful remove was performed.

<a name='T-eClearSdk-v1-Face-eClearPersonTagItem'></a>
## eClearPersonTagItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

Tags assigned to a person, will have this structure associated

<a name='P-eClearSdk-v1-Face-eClearPersonTagItem-TagName'></a>
### TagName `property`

##### Summary

The TagName that is associated to the person.

<a name='T-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem'></a>
## eClearPersonUpdateStatusByExternalKeyRequestItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Status

##### Summary

Request to update a persons status with their External Id Key and Value.

<a name='P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Key'></a>
### Key `property`

##### Summary

External Id Category name

<a name='P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Status'></a>
### Status `property`

##### Summary

Desired status for the persons record

<a name='P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem-Value'></a>
### Value `property`

##### Summary

External Id Category value

<a name='T-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyResponseItem'></a>
## eClearPersonUpdateStatusByExternalKeyResponseItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Status

##### Summary

Response to the requested update from [eClearPersonUpdateStatusByExternalKeyRequestItem](#T-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyRequestItem 'eClearSdk.v1.PersonManagement.Status.eClearPersonUpdateStatusByExternalKeyRequestItem')

<a name='P-eClearSdk-v1-PersonManagement-Status-eClearPersonUpdateStatusByExternalKeyResponseItem-Value'></a>
### Value `property`

##### Summary

If the update was applied successfully to the person

<a name='T-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem'></a>
## eClearPersonUpsertRequestItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Upsert

##### Summary

Request to update or add a person to the eClear database.

<a name='P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Key'></a>
### Key `property`

##### Summary

External Id Category name such as EmployeeId

<a name='P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Person'></a>
### Person `property`

##### Summary

The Person being added or updated in the eClear system

<a name='P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem-Value'></a>
### Value `property`

##### Summary

External Id Category value such as 12345

<a name='T-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertResponseItem'></a>
## eClearPersonUpsertResponseItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Upsert

##### Summary

The response to adding or updating a person in the eClear person database [eClearPersonUpsertRequestItem](#T-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertRequestItem 'eClearSdk.v1.PersonManagement.Upsert.eClearPersonUpsertRequestItem')

<a name='P-eClearSdk-v1-PersonManagement-Upsert-eClearPersonUpsertResponseItem-Value'></a>
### Value `property`

##### Summary

The response if the upsert was successfully added

<a name='T-eClearSdk-eClearSdkException'></a>
## eClearSdkException `type`

##### Namespace

eClearSdk

##### Summary

eClear Sdk Exception

<a name='M-eClearSdk-eClearSdkException-#ctor-System-String-'></a>
### #ctor(message) `constructor`

##### Summary

Exception captured in eClear Sdk

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| message | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') |  |

<a name='T-eClearSdk-eClearSdkFactory'></a>
## eClearSdkFactory `type`

##### Namespace

eClearSdk

##### Summary

eClear Sdk Factory - Object designed to prepare a connection to the eConnect eClear Message Bus

<a name='F-eClearSdk-eClearSdkFactory-ConnectionBuildLock'></a>
### ConnectionBuildLock `constants`

##### Summary

Async lock reference used to ensure publishing is done in a synchronous manor.

<a name='F-eClearSdk-eClearSdkFactory-ExchangeDefaultName'></a>
### ExchangeDefaultName `constants`

##### Summary

Bus Exchange name

<a name='P-eClearSdk-eClearSdkFactory-BusCache'></a>
### BusCache `property`

##### Summary

Holds the bus objects

<a name='M-eClearSdk-eClearSdkFactory-BusIdleEviction-System-Object,System-Object,Microsoft-Extensions-Caching-Memory-EvictionReason,System-Object-'></a>
### BusIdleEviction(key,value,reason,state) `method`

##### Summary

Cleanup when the Bus element is expired since it hasn't been accessed in the sliding period

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| key | [System.Object](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Object 'System.Object') |  |
| value | [System.Object](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Object 'System.Object') |  |
| reason | [Microsoft.Extensions.Caching.Memory.EvictionReason](#T-Microsoft-Extensions-Caching-Memory-EvictionReason 'Microsoft.Extensions.Caching.Memory.EvictionReason') |  |
| state | [System.Object](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Object 'System.Object') |  |

<a name='M-eClearSdk-eClearSdkFactory-GetReadySdk-MessageBus-RabbitMqCredentials,System-Boolean-'></a>
### GetReadySdk(creds,allowBusCleanup) `method`

##### Summary

Get the FaceRec SDK with the RabbitMqCredentials, typically received by the Mesh system

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| creds | [MessageBus.RabbitMqCredentials](#T-MessageBus-RabbitMqCredentials 'MessageBus.RabbitMqCredentials') |  |
| allowBusCleanup | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') |  |

<a name='M-eClearSdk-eClearSdkFactory-GetReadySdk-System-String,System-Boolean-'></a>
### GetReadySdk(connectionString,allowBusCleanup) `method`

##### Summary

Default Factory - Get a ready SDK object. This factory does cache objects, so its safe to re-request by connection string and no IO operation will occur
if the object is already created.

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| connectionString | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Connection String (or yml file) of the Message Bus. |
| allowBusCleanup | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | If you plan to cache this object, and not use the factory (which handles its own caching), set this to false. This will prevent it from being cleaned up. |

<a name='M-eClearSdk-eClearSdkFactory-GetReadySdk-System-String,System-String,System-Boolean,System-Boolean-'></a>
### GetReadySdk(connectionString,durable,allowBusCleanup,exchange) `method`

##### Summary

Get a ready SDK object. This factory does cache objects, so its safe to re-request by connection string and no IO operation will occur
if the object is already created.

##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| connectionString | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Connection String (or yml file) of the Message Bus. |
| durable | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Is the exchange durable? |
| allowBusCleanup | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | If you plan to cache this object, and not use the factory (which handles its own caching), set this to false. This will prevent it from being cleaned up. |
| exchange | [System.Boolean](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Boolean 'System.Boolean') | The Exchange name (default eclear.tx) to publish/subscribe messages with |

<a name='M-eClearSdk-eClearSdkFactory-GetSdkFromConnectionString-System-String-'></a>
### GetSdkFromConnectionString(connectionString) `method`

##### Summary

Gets a ready eClear Sdk object. Caller is responsible for object lifetime. It is recommended that this
object to managed as a single object throughout the application, which will reduce resource requirements

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| connectionString | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | Raw connection string |

<a name='M-eClearSdk-eClearSdkFactory-GetSdkFromRabbitMqCredentials-MessageBus-RabbitMqCredentials-'></a>
### GetSdkFromRabbitMqCredentials(rabbitMqCredentials) `method`

##### Summary

Gets a ready eClear Sdk object. Caller is responsible for object lifetime. It is recommended that this
object to managed as a single object throughout the application, which will reduce resource requirements

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| rabbitMqCredentials | [MessageBus.RabbitMqCredentials](#T-MessageBus-RabbitMqCredentials 'MessageBus.RabbitMqCredentials') | Credential Object |

<a name='M-eClearSdk-eClearSdkFactory-GetSdkFromYamlFile-System-String-'></a>
### GetSdkFromYamlFile(ymlFile) `method`

##### Summary

Gets a ready eClear Sdk object. Caller is responsible for object lifetime. It is recommended that this
object to managed as a single object throughout the application, which will reduce resource requirements

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| ymlFile | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | File path where the yaml doc exists with the connection information |

<a name='M-eClearSdk-eClearSdkFactory-GetSdkFromYamlString-System-String-'></a>
### GetSdkFromYamlString(ymlString) `method`

##### Summary

Gets a ready eClear Sdk object. Caller is responsible for object lifetime. It is recommended that this
object to managed as a single object throughout the application, which will reduce resource requirements

##### Returns

Ready eConnect Sdk [IeClearSdk](#T-eClearSdk-IeClearSdk 'eClearSdk.IeClearSdk')

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| ymlString | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | the Yaml document with the connection information |

<a name='T-eClearSdk-eClearSdkNonDisposable'></a>
## eClearSdkNonDisposable `type`

##### Namespace

eClearSdk

<a name='M-eClearSdk-eClearSdkNonDisposable-AddUsage'></a>
### AddUsage() `method`

##### Summary

Mark another process using this object to prevent removal

##### Parameters

This method has no parameters.

<a name='M-eClearSdk-eClearSdkNonDisposable-Dispose'></a>
### Dispose() `method`

##### Summary

Dispose to remove the usage handle.

##### Parameters

This method has no parameters.

<a name='M-eClearSdk-eClearSdkNonDisposable-Teardown'></a>
### Teardown() `method`

##### Summary

Internal API to close this connection and any handles. This should be used by
the connection pooler only.

##### Parameters

This method has no parameters.

<a name='T-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem'></a>
## eClearSearchByExternalIdRequestItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Query

##### Summary

Search Request to get an eClear person object.

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-IncludePhoto'></a>
### IncludePhoto `property`

##### Summary

Include the photo with the request. Note this adds a considerable amount of byte data to the payload.

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-Key'></a>
### Key `property`

##### Summary

External Id category name

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem-Value'></a>
### Value `property`

##### Summary

External Id category value

<a name='T-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdResponseItem'></a>
## eClearSearchByExternalIdResponseItem `type`

##### Namespace

eClearSdk.v1.PersonManagement.Query

##### Summary

Search response to [eClearSearchByExternalIdRequestItem](#T-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdRequestItem 'eClearSdk.v1.PersonManagement.Query.eClearSearchByExternalIdRequestItem')

<a name='P-eClearSdk-v1-PersonManagement-Query-eClearSearchByExternalIdResponseItem-PersonItem'></a>
### PersonItem `property`

##### Summary

Person Response matching the requested query

<a name='T-eClearSdk-v1-Face-eClearServerInfoItem'></a>
## eClearServerInfoItem `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

Server Information Container

<a name='P-eClearSdk-v1-Face-eClearServerInfoItem-SystemId'></a>
### SystemId `property`

##### Summary

Unique server where the message originated from

<a name='P-eClearSdk-v1-Face-eClearServerInfoItem-SystemName'></a>
### SystemName `property`

##### Summary

An administratively assigned Id managed by the deployment. This may be a customer name. This name is managed by eConnect

<a name='T-eClearSdk-v1-PersonManagement-eClearTagItem'></a>
## eClearTagItem `type`

##### Namespace

eClearSdk.v1.PersonManagement

##### Summary

eClear Tag, the logical grouping that can be applied to a persons record.

<a name='P-eClearSdk-v1-PersonManagement-eClearTagItem-TagName'></a>
### TagName `property`

##### Summary

The Name of the Tag such as "Security" or "HR"

<a name='T-eClearSdk-v1-ePass-ePassReportMetadata'></a>
## ePassReportMetadata `type`

##### Namespace

eClearSdk.v1.ePass

##### Summary

Key/Value container for additional metadata associated to the ePass report

<a name='P-eClearSdk-v1-ePass-ePassReportMetadata-Key'></a>
### Key `property`

##### Summary

Lookup key for the metadata

<a name='P-eClearSdk-v1-ePass-ePassReportMetadata-Value'></a>
### Value `property`

##### Summary

Value associated to the Key in this object.

<a name='T-eClearSdk-v1-Face-ePassReportResult'></a>
## ePassReportResult `type`

##### Namespace

eClearSdk.v1.Face

##### Summary

ePass Report Results

<a name='F-eClearSdk-v1-Face-ePassReportResult-Fail'></a>
### Fail `constants`

##### Summary

A matching ePass Fail was attached to this record

<a name='F-eClearSdk-v1-Face-ePassReportResult-NoSubmission'></a>
### NoSubmission `constants`

##### Summary

No submission was found

<a name='F-eClearSdk-v1-Face-ePassReportResult-Pass'></a>
### Pass `constants`

##### Summary

A matching ePass Pass was attached to this record

<a name='T-eClearSdk-v1-ePass-ePassResultItem'></a>
## ePassResultItem `type`

##### Namespace

eClearSdk.v1.ePass

##### Summary

Normalized eConnect ePass Result used within the eClear system if enabled

<a name='P-eClearSdk-v1-ePass-ePassResultItem-DateTimeUtc'></a>
### DateTimeUtc `property`

##### Summary

The UTC time of the report

<a name='P-eClearSdk-v1-ePass-ePassResultItem-Email'></a>
### Email `property`

##### Summary

Email address of the person from the report system

<a name='P-eClearSdk-v1-ePass-ePassResultItem-FirstName'></a>
### FirstName `property`

##### Summary

First name from the report system

<a name='P-eClearSdk-v1-ePass-ePassResultItem-LastName'></a>
### LastName `property`

##### Summary

Last name from the report system

<a name='P-eClearSdk-v1-ePass-ePassResultItem-Metadata'></a>
### Metadata `property`

##### Summary

Extra metadata for the report.

<a name='P-eClearSdk-v1-ePass-ePassResultItem-Pass'></a>
### Pass `property`

##### Summary

The Pass or Fail result

<a name='P-eClearSdk-v1-ePass-ePassResultItem-PersonId'></a>
### PersonId `property`

##### Summary

The Person ID associated to the default external ID in the eClear system

<a name='P-eClearSdk-v1-ePass-ePassResultItem-ReferenceId'></a>
### ReferenceId `property`

##### Summary

The reference ID of the remote report. This can be used for lookups within the 3rd party application
