---
title: MAPI 常量
manager: soliver
ms.date: 10/02/2018
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8fa5ac8d-3f63-499c-bb4e-439984773e4a
description: 常量定义、MAPI 接口声明，以及 MAPI API 使用的类和接口标识符。
ms.openlocfilehash: 343b777550d88276a1f5cad19f12ae7fc09c6244
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318919"
---
# <a name="mapi-constants"></a>MAPI 常量

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含常量定义、MAPI 接口声明，以及 MAPI API 使用的类和接口标识符。
  
## <a name="class-and-interface-identifiers"></a>类和接口标识符

使用在 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_GUID 宏，将全局唯一标识符 (GUID) 符号名称与其值关联起来，除非另有说明。
  
## <a name="attachment-security-conversion-api"></a>附件安全转换 API

本部分包含常量定义和附件安全 API 的接口标识符。
  
```cpp
// {b2533636-c3f3-416f-bf04-aefe41abaae2}
DEFINE_GUID(IID_IAttachmentSecurity, 0xb2533636, 0xc3f3, 0x416f, 0xbf, 0x04, 0xae, 0xfe, 0x41, 0xab, 0xaa, 0xe2);
```

使用在 Windows SDK 头文件 mapidefs.h 中定义的 MAPIMETHOD 宏来定义纯虚函数 **[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**。 
  
```cpp
#define MAPI_IATTACHMENTSECURITY_METHODS(IPURE)         MAPIMETHOD(IsAttachmentBlocked)         (LPCWSTR pwszFileName, BOOL *pfBlocked) IPURE;
```

使用在 Windows SDK 头文件 mapidefs.h 中定义的 DECLARE_MAPI_INTERFACE_ 宏来定义 **[IAttachmentSecurity](iattachmentsecurityiunknown.md)** 的虚拟方法表。 
  
```cpp
DECLARE_MAPI_INTERFACE_(IAttachmentSecurity, IUnknown) 
{ 
    BEGIN_INTERFACE 
    MAPI_IUNKNOWN_METHODS(PURE) 
    MAPI_IATTACHMENTSECURITY_METHODS(PURE) 
};
```

## <a name="mapi-mime-conversion-api"></a>MAPI-MIME 转换 API

本部分包含常量定义和 MAPI-MIME 转换 API 的类和接口标识符。
  
### <a name="constants"></a>常量

|||
|:-----|:-----|
|CCSF_SMTP  <br/> |0x0002  <br/> |
|CCSF_NOHEADERS  <br/> |0x0004  <br/> |
|CCSF_USE_TNEF  <br/> | 0x0010  <br/> |
|CCSF_INCLUDE_BCC  <br/> |0x0020  <br/> |
|CCSF_8BITHEADERS  <br/> | 0x0040  <br/> |
|CCSF_USE_RTF  <br/> |0x0080  <br/> |
|CCSF_PLAIN_TEXT_ONLY  <br/> |0x1000  <br/> |
|CCSF_NO_MSGID  <br/> |0x4000  <br/> |
|CCSF_GLOBAL_MESSAGE  <br/> |0x00200000  <br/> |
|E_INVALIDARG  <br/> | *如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义*  <br/> |
   
### <a name="class-identifiers"></a>类标识符

```cpp
// {4e3a7680-b77a-11d0-9da5-00c04fd65685}
DEFINE_GUID(CLSID_IConverterSession, 0x4e3a7680, 0xb77a, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

### <a name="interface-identifiers"></a>接口标识符

```cpp
// {4b401570-b77b-11d0-9da5-00c04fd65685}
DEFINE_GUID(IID_IConverterSession, 0x4b401570, 0xb77b, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

## <a name="offline-state-api"></a>脱机状态 API

本部分包含常量定义和脱机状态 API 的类和接口标识符。
  
### <a name="constants"></a>常量

|||
|:-----|:-----|
|E_INVALIDARG  <br/> | *如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义*  <br/> |
|E_NOINTERFACE  <br/> | *如 Windows (SDK) 头文件 winerror.h 中所定义*  <br/> |
|MAPIOFFLINE_ADVISE_DEFAULT  <br/> |(ULONG)0  <br/> |
|MAPIOFFLINE_UNADVISE_DEFAULT  <br/> |(ULONG)0  <br/> |
|MAPIOFFLINE_ADVISE_TYPE_STATECHANGE  <br/> |1  <br/> |
|MAPIOFFLINE_CAPABILITY_OFFLINE  <br/> |0x1  <br/> |
|MAPIOFFLINE_CAPABILITY_ONLINE  <br/> |0x2  <br/> |
|MAPIOFFLINE_FLAG_BLOCK  <br/> |0x00002000  <br/> |
|MAPIOFFLINE_FLAG_DEFAULT  <br/> |0x00000000  <br/> |
|MAPIOFFLINE_STATE_ALL  <br/> |0x003f037f  <br/> |
|**联机或脱机** <br/> ||
|MAPIOFFLINE_STATE_OFFLINE_MASK  <br/> |0x00000003  <br/> |
|MAPIOFFLINE_STATE_OFFLINE  <br/> |0x00000001  <br/> |
|MAPIOFFLINE_STATE_ONLINE  <br/> |0x00000002  <br/> |
   
### <a name="class-identifiers"></a>类标识符

```cpp
//{fbeffd93-b11f-4094-842b-96dcd31e63d1}
DEFINE_GUID(GUID_GlobalState, 0xfbeffd93, 0xb11f, 0x4094, 0x84, 0x2b, 0x96, 0xdc, 0xd3, 0x1e, 0x63, 0xd1);
```

### <a name="interface-identifiers"></a>接口标识符

```cpp
//{000672B5-0000-0000-c000-000000000046}
DEFINE_GUID(IID_IMAPIOffline, 0x000672B5, 0x0000, 0x0000, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);
```

```cpp
//{0317bde5-fc29-44cd-8dcd-36125a3be9ec}
DEFINE_GUID(IID_IMAPIOfflineNotify, 0x0317bde5, 0xfc29, 0x44cd, 0x8d, 0xcd, 0x36, 0x12, 0x5a, 0x3b, 0xe9, 0xec);
```

```cpp
//{42175607-ff3e-4790-bc18-66c8643e6424
DEFINE_GUID(IID_IMAPIOfflineMgr, 0x42175607, 0xFF3E, 0x4790, 0xbc, 0x18, 0x66, 0xc8, 0x64, 0x3e, 0x64, 0x24);
```

## <a name="outlook-named-properties"></a>Outlook 命名属性

本部分包含命名属性的常量定义及其命名空间和其他相关常量。
  
### <a name="definitions-for-named-properties"></a>命名属性定义

```cpp
#define dispidMeetingType0x0026 
#define dispidFileUnder0x8005 
#define dispidYomiFirstName 0x802C 
#define dispidYomiLastName 0x802D 
#define dispidYomiCompanyName 0x802E 
#define dispidWorkAddressStreet 0x8045 
#define dispidWorkAddressCity 0x8046 
#define dispidWorkAddressState 0x8047 
#define dispidWorkAddressPostalCode 0x8048 
#define dispidWorkAddressCountry 0x8049 
#define dispidWorkAddressPostOfficeBox 0x804A 
#define dispidInstMsg 0x8062 
#define dispidEmailDisplayName 0x8080 
#define dispidEmailAddrType 0x8082 
#define dispidEmailEmailAddress 0x8083 
#define dispidEmailOriginalDisplayName 0x8084 
#define dispidEmail1OriginalEntryID0x8085 
#define dispidEmail2DisplayName 0x8090 
#define dispidEmail2AddrType 0x8092 
#define dispidEmail2EmailAddress 0x8093 
#define dispidEmail2OriginalDisplayName 0x8094 
#define dispidEmail2OriginalEntryID0x8095 
#define dispidEmail3DisplayName 0x80A0 
#define dispidEmail3AddrType 0x80A2 
#define dispidEmail3EmailAddress 0x80A3 
#define dispidEmail3OriginalDisplayName 0x80A4 
#define dispidEmail3OriginalEntryID0x80A5 
#define dispidTaskStatus 0x8101 
#define dispidTaskStartDate 0x8104 
#define dispidTaskDueDate 0x8105 
#define dispidTaskActualEffort 0x8110 
#define dispidTaskEstimatedEffort 0x8111 
#define dispidTaskFRecur 0x8126 
#define dispidBusyStatus0x8205 
#define dispidLocation 0x8208 
#define dispidApptStartWhole 0x820D 
#define dispidApptEndWhole 0x820E 
#define dispidApptDuration 0x8213 
#define dispidRecurring 0x8223 
#define dispidTimeZoneStruct0x8233 
#define dispidAllAttendeesString 0x8238 
#define dispidToAttendeesString 0x823B 
#define dispidCCAttendeesString 0x823C 
#define dispidConfCheck0x8240 
#define dispidApptCounterProposal 0x8257 
#define dispidApptTZDefStartDisplay0x825E 
#define dispidApptTZDefEndDisplay0x825F 
#define dispidApptTZDefRecur0x8260 
#define dispidReminderTime0x8502 
#define dispidReminderSet 0x8503 
#define dispidFormStorage0x850F 
#define dispidPageDirStream0x8513 
#define dispidSmartNoAttach 0x8514 
#define dispidCommonStart 0x8516 
#define dispidCommonEnd 0x8517 
#define dispidFormPropStream0x851B 
#define dispidRequest 0x8530 
#define dispidCompanies 0x8539 
#define dispidContacts0x853A 
#define dispidPropDefStream0x8540 
#define dispidScriptStream0x8541 
#define dispidCustomFlag0x8542 
#define dispidReminderNextTime 0x8560 
#define dispidHeaderItem0x8578 
#define dispidUseTNEF0x8582 
#define dispidToDoTitle0x85A4 
#define dispidLogType 0x8700 
#define dispidLogStart 0x8706 
#define dispidLogDuration 0x8707 
#define dispidLogEnd 0x8708 
```

### <a name="definitions-for-namespaces"></a>命名空间定义

以下全局唯一标识符 (GUID) 代表命名属性的命名空间。
  
```cpp
const GUID PS_INTERNET_HEADERS  = {0x00020386, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PS_PUBLIC_STRINGS    = {0x00020329, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Appointment= {0x00062002, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Address       = {0x00062004, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Common        = {0x00062008, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Log           = {0x0006200A, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Meeting = {0x6ED8DA90, 0x450B, 0x101B, {0x98, 0xDA, 0x00, 0xAA, 0x00, 0x3F, 0x13, 0x05}}; 
const GUID PSETID_Task          = {0x00062003, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
```

参考 PSETID 定义的 MAPI 存储部分。
  
### <a name="other-constants"></a>其他常量

|||
|:-----|:-----|
|INSP_ONEOFFFLAGS  <br/> |0xD000000  <br/> |
|INSP_PROPDEFINITION  <br/> |0x2000000  <br/> |
|MNID_ID  <br/> | *如头文件 mapidefs.h 中所定义。*  <br/> |
|MNID_STRING  <br/> | *如头文件 mapidefs.h 中所定义。*  <br/> |
|mtgNone  <br/> |0x0  <br/> |
|mtgRequest  <br/> |0x00000001  <br/> |
|mtgFullUpdate  <br/> |0x00010000  <br/> |
|mtgInfoUpdate  <br/> |0x00020000  <br/> |
|mtgOutofDate  <br/> |0x00080000  <br/> |
|mtgDelegated  <br/> |0x00100000  <br/> |
   
## <a name="replication-api"></a>复制 API

本部分包含常量定义、MAPI 接口声明，以及复制 API 的类和接口标识符。
  
### <a name="constants"></a>常量

下面是识别 MAPI 服务提供商的 [MAPIUID](mapiuid.md) 结构： 
  
```cpp
const MAPIUID g_muidProvPrvNST = 
 { 0xE9, 0x2F, 0xEB, 0x75, 0x96, 0x50, 0x44, 0x86, 
      0x83, 0xB8, 0x7D, 0xE5, 0x22, 0xAA, 0x49, 0x48 };
```

|||
|:-----|:-----|
|DNH_OK  <br/> |0x00010000  <br/> |
|DNT_OK  <br/> |0x00010000  <br/> |
|HSF_LOCAL  <br/> |0x00000008  <br/> |
|HSF_COPYDESTRUCTIVE  <br/> |0x00000010  <br/> |
|HSF_OK  <br/> |0x00010000  <br/> |
|MDB_OST_LOGON_UNICODE  <br/> |((ULONG) 0x00000800)  <br/> |
|MDB_OST_LOGON_ANSI  <br/> |((ULONG) 0x00001000)  <br/> |
|SHOW_SOFT_DELETES  <br/> |((ULONG) 0x00000002)  <br/> |
|SS_ACTIVE  <br/> |0  <br/> |
|SS_SUSPENDED  <br/> |1  <br/> |
|SYNC_UPLOAD_HIERARCHY  <br/> |0x00000001  <br/> |
|SYNC_DOWNLOAD_HIERARCHY  <br/> |0x00000002  <br/> |
|SYNC_UPLOAD_CONTENTS  <br/> |0x00000040  <br/> |
|SYNC_DOWNLOAD_CONTENTS  <br/> |0x00000080  <br/> |
|SYNC_OUTGOING_MAIL  <br/> |0x00000200  <br/> |
|SYNC_BACKGROUND  <br/> |0x00001000  <br/> |
|SYNC_THESE_FOLDERS  <br/> |0x00020000  <br/> |
|SYNC_HEADERS  <br/> |0x02000000  <br/> |
|UPC_OK  <br/> |0x00010000  <br/> |
|UPD_ASSOC  <br/> |0x00000001  <br/> |
|UPD_MOV  <br/> |0x00000002  <br/> |
|UPD_OK  <br/> |0x00010000  <br/> |
|UPD_MOVED  <br/> |0x00020000  <br/> |
|UPD_UPDATE  <br/> |0x00040000  <br/> |
|UPD_COMMIT  <br/> |0x00080000  <br/> |
|UPF_NEW  <br/> |0x00000001  <br/> |
|UPF_MOD_PARENT  <br/> |0x00000002  <br/> |
|UPF_MOD_PROPS  <br/> |0x00000004  <br/> |
|UPF_DEL  <br/> |0x00000008  <br/> |
|UPF_OK  <br/> |0x00010000  <br/> |
|UPH_OK  <br/> |0x00010000  <br/> |
|UPM_ASSOC  <br/> |0x00000001  <br/> |
|UPM_NEW  <br/> |0x00000002  <br/> |
|UPM_MOV  <br/> |0x00000004  <br/> |
|UPM_MOD_PROPS  <br/> |0x00000008  <br/> |
|UPM_HEADER  <br/> |0x00000010  <br/> |
|UPM_OK  <br/> |0x00010000  <br/> |
|UPM_MOVED  <br/> |0x00020000  <br/> |
|UPM_COMMIT  <br/> |0x00040000  <br/> |
|UPM_DELETE  <br/> |0x00080000  <br/> |
|UPM_SAVE  <br/> |0x00100000  <br/> |
|UPR_ASSOC  <br/> |0x00000001  <br/> |
|UPR_READ  <br/> |0x00000002  <br/> |
|UPR_OK  <br/> |0x00010000  <br/> |
|UPR_COMMIT  <br/> |0x00020000  <br/> |
|UPS_UPLOAD_ONLY  <br/> |0x00000001  <br/> |
|UPS_DNLOAD_ONLY  <br/> |0x00000002  <br/> |
|UPS_ONE_FOLDER  <br/> |0x00000004  <br/> |
|UPS_THESE_FOLDERS  <br/> |0x00000080  <br/> |
|UPS_OK  <br/> |0x00010000  <br/> |
|UPT_OK  <br/> |0x00010000  <br/> |
|UPT_PUBLIC  <br/> |0x00000001  <br/> |
|UPV_ERROR  <br/> |0x00010000  <br/> |
|UPV_DIRTY  <br/> |0x00020000  <br/> |
|UPV_COMMIT  <br/> |0x00040000  <br/> |
   
### <a name="interface-declarations"></a>接口声明

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportHierarchyChanges,PXIHC);
```

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportContentsChanges,PXICC);
```

### <a name="interface-identifiers"></a>接口标识符

```cpp
//{4FDEEFF0-0319-11CF-B4CF-00AA0DBBB6E6}
DEFINE_GUID (IID_IPSTX, 0x4FDEEFF0, 0x0319, 0x11CF, 0xB4, 0xCF, 0x00, 0xAA, 0x0D, 0xBB, 0xB6, 0xE6)
```

```cpp
//{2067A790-2A45-11D1-EB86-00A0C90DCA6D}
DEFINE_GUID (IID_IPSTX2, 0x2067A790, 0x2A45, 0x11D1, 0xEB, 0x86, 0x00, 0xA0, 0xC9, 0x0D, 0xCA, 0x6D)
```

```cpp
//{55f15320-111b-11d2-a999-006008b05aa7}
DEFINE_GUID (IID_IPSTX3, 0x55f15320, 0x111b, 0x11d2, 0xa9, 0x99, 0x00, 0x60, 0x08, 0xb0, 0x5a, 0xa7)
```

```cpp
//{aa2e2092-ac08-11d2-a2f9-0060b0ec3d4f}
DEFINE_GUID (IID_IPSTX4, 0xaa2e2092, 0xac08, 0x11d2, 0xa2, 0xf9, 0x00, 0x60, 0xb0, 0xec, 0x3d, 0x4f)
```

```cpp
//{55f15322-111b-11d2-a999-006008b05aa7}
DEFINE_GUID (IID_IPSTX5, 0x55f15322, 0x111b, 0x11d2, 0xa9, 0x99, 0x00, 0x60, 0x08, 0xb0, 0x5a, 0xa7)
```

```cpp
//{55f15323-111b-11d2-a999-006008b05aa7}
DEFINE_GUID (IID_IPSTX6, 0x55f15323, 0x111b, 0x11d2, 0xa9, 0x99, 0x00, 0x60, 0x08, 0xb0, 0x5a, 0xa7)
```

```cpp
//{d2d85db4-840f-49b8-9982-07d2405ec6b7}
DEFINE_GUID (IID_IOSTX, 0xd2d85db4,  0x840f, 0x49b8, 0x99, 0x82, 0x07, 0xd2, 0x40, 0x5e, 0xc6, 0xb7)
```

<br/>

将以下两个接口标识符与 [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、[IMAPISession::OpenEntry](imapisession-openentry.md) 或 [IMsgStore::OpenEntry](imsgstore-openentry.md) 配合使用以分别打开并忽略针对文件夹对象和邮件对象的任何提供商检查。 
  
```cpp
//{57D333A0-F589-4b23-A3F9-85F82FEC153C}
DEFINE_GUID (IID_IMAPIFolderNoProvChk, 0x57D333A0, 0xF589, 0x4b23, 0xA3, 0xF9, 0x85, 0xF8, 0x2F, 0xEC, 0x15, 0x3C)
```

```cpp
//{C3505457-7B2E-4c3b-A8D6-6DD949BB97A1}
DEFINE_GUID (IID_IMessageNoProvChk, 0xC3505457, 0x7B2E, 0x4c3b, 0xA8, 0xD6, 0x6D, 0xD9, 0x49, 0xBB, 0x97, 0xA1)
```

## <a name="mapi-store"></a>MAPI 存储

本部分包含常量定义和 API 使用的与 MAPI 存储接合的接口标识符。
  
### <a name="constants"></a>常量

||||
|:-----|:-----|:-----|
|fnevIndexing  <br/> |((ULONG) 0x00010000)  <br/> |存储提供程序可以指定**[通知](notification.md)** 结构 **ulEventType** 成员中的 **fnevIndexing**，以通知索引器对象已准备好进行索引。 **通知**结构的 **info** 成员包含 **[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。  <br/> |
|FS_NONE  <br/> |0x00  <br/> |客户端可以调用 **[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** 并检查返回的位掩码。 **FS_NONE** 指示文件夹不支持共享。  <br/> |
|FS_SUPPORTS_SHARING  <br/> |0x01  <br/> |客户端可以调用 **IFolderSupport::GetSupportMask** 并检查返回的位掩码。 **FS_SUPPORTS_SHARING** 指示文件夹支持共享。  <br/> |
|INDEXING_SEARCH_OWNER  <br/> |((ULONG) 0x00000001)  <br/> |标识将通知推送到索引器指示对象已准备好索引的进程。  <br/> |
|MNID_ID  <br/> |如 Microsoft Windows 软件开发工具包 (SDK) 头文件 mapidefs.h 中所定义的  <br/> |**[MAPINAMEID](mapinameid.md)** 结构的 **ulKind** 字段的值。  <br/> |
|MNID_STRING  <br/> |如 Microsoft Windows 软件开发工具包 (SDK) 头文件 mapidefs.h 中所定义。  <br/> |**[MAPINAMEID](mapinameid.md)** 结构的 **ulKind** 字段的值。  <br/> |
|MSCAP_RES_ANNOTATION  <br/> |((ULONG) 0x00000001)  <br/> |如果客户端为 **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)** 指定 *mscapSelector* 中的 **MSCAP_SEL_RESTRICTION**，如果存储忽略限制中的无效参数，则 **GetCapabilities** 可能会返回该值。  <br/> |
|MSCAP_SECURE_FOLDER_HOMEPAGES  <br/> |((ULONG) 0x00000020)  <br/> |如果客户端为 **IMSCapabilities::GetCapabilities** 指定 *mscapSelector* 中的 **MSCAP_SEL_FOLDER**，如果存储是支持文件夹主页的非默认存储，则 **GetCapabilities** 可能会返回该值。  <br/> |
|STORE_PUSHER_OK  <br/> |((ULONG) 0x00800000)  <br/> |客户端可以获取属性 **[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 来确定邮件存储的特征。 如果存储提供程序在位掩码中设置 **STORE_PUSHER_OK** 标记，这意味着 MAPI 协议处理程序不会对存储区进行爬网，且存储区负责通过通知将任何更改推送到索引器来索引邮件。  <br/> |
   
### <a name="definitions-for-namespaces"></a>命名空间定义

以下全局唯一标识符 (GUID) 代表命名属性的命名空间。 他们已通过 MAPI 协议处理程序 (PH) 编制索引，并被记录为只读。
  
> [!CAUTION]
> 命名属性不应用于创建或修改项。 
  
```cpp
const GUID PS_INTERNET_HEADERS  = {0x00020386, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PS_PUBLIC_STRINGS    = {0x00020329, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Address       = {0x00062004, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Appointment   = {0x00062002, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Common        = {0x00062008, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Log           = {0x0006200A, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
const GUID PSETID_Meeting       = {0x6ED8DA90, 0x450B, 0x101B, {0x98, 0xDA, 0x00, 0xAA, 0x00, 0x3F, 0x13, 0x05}}; 
const GUID PSETID_Task          = {0x00062003, 0x0000, 0x0000, {0xC0, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x46}}; 
```

#### <a name="mnidid-properties"></a>MNID_ID Properties
  
```cpp
// In PSETID_Address
#define dispidWorkAddressStreet 0x8045
#define dispidWorkAddressCity 0x8046
#define dispidWorkAddressState 0x8047
#define dispidWorkAddressPostalCode 0x8048
#define dispidWorkAddressCountry 0x8049
#define dispidInstMsg 0x8062
#define dispidEmailDisplayName 0x8080
#define dispidEmailOriginalDisplayName 0x8084
```

```cpp
// In PSETID_Appointment
#define dispidLocation 0x8208
#define dispidApptStartWhole 0x820D
#define dispidApptEndWhole 0x820E
#define dispidApptDuration 0x8213
#define dispidRecurring 0x8223
#define dispidAllAttendeesString 0x8238
#define dispidToAttendeesString 0x823B
#define dispidCCAttendeesString 0x823C
```

```cpp
// In PSETID_Common
#define dispidReminderSet 0x8503
#define dispidSmartNoAttach 0x8514
#define dispidCommonStart 0x8516
#define dispidCommonEnd 0x8517
#define dispidRequest 0x8530
#define dispidCompanies 0x8539
#define dispidReminderNextTime 0x8560
```

```cpp
// In PSETID_Log (also known as Journal)
#define dispidLogType 0x8700
#define dispidLogStart 0x8706
#define dispidLogDuration 0x8707
#define dispidLogEnd 0x8708MNID_STRING properties
```

```cpp
// In PSETID_Task
#define dispidTaskStartDate 0x8104
#define dispidTaskDueDate 0x8105
#define dispidTaskActualEffort 0x8110
#define dispidTaskEstimatedEffort 0x8111
#define dispidTaskFRecur 0x8126
```

#### <a name="mnidstring-properties"></a>MNID_STRING Properties
  
```cpp
// In PS_PUBLIC_STRINGS 
"Keywords"
```

```cpp
// In PS_INTERNET_HEADERS
"return-path"
```

### <a name="interface-identifiers"></a>接口标识符

```cpp
//{00375ac3-ecaf-4ef8-a527-34f452fa9c67}
DEFINE_GUID(IID_IFolderSupport, 0x00375ac3, 0xecaf, 0x4ef8, 0xa5, 0x27, 0x34, 0xf4, 0x52, 0xfa, 0x9c, 0x67);

```

```cpp
//{29F3AB10-554d-11d0-a97c-00a0c911f50a}
#define DEFINE_PRXGUID(_name, _l) DEFINE_GUID(_name, (0x29f3ab10 + _l), 0x554d, 0x11d0, 0xa9, 0x7c, 0x00, 0xa0, 0xc9, 0x11, 0xf5, 0x0a) 
DEFINE_PRXGUID(IID_IProxyStoreObject, 0x00000000L);
```

使用在 Windows SDK 头文件 guiddef.h 中定义的 `DEFINE_OLEGUID` 宏将以下 GUID 符号名称与及其值相关联。 
  
```cpp
//{00020393-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_IMSCapabilities, 0x00020393, 0, 0)

```

## <a name="mapi-address-book-constants"></a>MAPI 通讯簿常量

本部分包含 MAPI 通讯簿的常量定义。
  
### <a name="constants"></a>常量

||||
|:-----|:-----|:-----|
|CONTAB_ROOT  <br/> |((ULONG) 0x00000001)  <br/> |MAPI 通讯簿对象的根文件夹。  <br/> |
|CONTAB_SUBROOT  <br/> |((ULONG) 0x00000002)  <br/> |MAPI 通讯簿对象的根文件夹内包含一个子文件。  <br/> |
|CONTAB_CONTAINER  <br/> |((ULONG) 0x00000003)  <br/> |通讯簿容器对象。  <br/> |
|CONTAB_USER  <br/> |((ULONG) 0x00000004)  <br/> |消息传递用户对象。  <br/> |
|CONTAB_DISTLIST  <br/> |((ULONG) 0x00000005)  <br/> |通讯组列表对象。  <br/> |
   
## <a name="additional-mapi-constants"></a>其他 MAPI 常量

本部分包含包括错误代码在内的常量定义，和以前未公开和记录的 MAPI API 使用的接口标识符。
  
||||
|:-----|:-----|:-----|
|DIALOG_MODAL  <br/> |((ULONG) 0x00000001)  <br/> |当客户端调用 [IAddrBook::Details](iaddrbook-details.md) 方法时，客户端必须在 _ulFlags_ 参数中设置 **DIALOG_MODAL** 标记，以显示模式对话框框，其中显示了有关特定通讯簿条目的详细信息。 此常量在 mapidefs.h 中定义。  <br/> |
|ITEMPROC_FORCE  <br/> |0x00000800  <br/> |在 Outlook 2007 中，包装的 PST 存储区会在通知 MAPI 客户端新邮件之前，对新邮件执行规则和垃圾邮件筛选处理。 使用 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 方法在 PST 存储区中创建新邮件的提供商或客户端应在 [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法的 _ulFlags_ 参数中设置 **ITEMPROC_FORCE** 标记，以便向 PST 存储区表明，在存储区通知任何侦听客户端有关新邮件到达之前，该邮件有资格进行规则处理。 请注意，此类规则处理仅适用于在除 Microsoft Exchange Server 以外的服务器上创建的新邮件，因为 Exchange Server 处理服务器上的邮件规则。 因此创建邮件的提供商或客户端必须将此标记与 **NON_EMS_XP_SAVE** 一起传递，表示服务器不是 Exchange 服务器。  <br/> |
| MAPI_BG_SESSION  <br/> |0x00200000  <br/> |客户端可以调用 [MAPILogonEx](mapilogonex.md) 函数，设置 _flFlags_ 参数中的 **MAPI_BG_SESSION** 标记，以登录到会话并在后台执行任何操作。 一般情况下，如果客户端打算在后台线程，或者在独立过程中以在前台线程上不显眼的方式执行处理，它应调用带 **MAPI_BG_SESSION** 标记的 [MAPILogonEx](mapilogonex.md)。 使用此方法的一个示例是客户端应用程序，例如索引引擎，它会打开用于后台类型访问的个人文件夹文件 (PST)。  <br/> |
|MAPI_CACHE_ONLY  <br/> |0x00004000  <br/> |客户端可以调用 [IAddrBook::OpenEntry](iaddrbook-openentry.md) 方法时，设置 _ulFlags_ 参数中的 **MAPI_CACHE_ONLY** 标记来打开通讯簿条目，随后仅从缓存中访问它。 使用此方法的一个示例是想要在缓存 Exchange 模式中打开全局地址列表，并从缓存访问该通讯簿条目的客户端应用程序，而无需在客户端和服务器之间创建流量。  <br/> |
|MAPI_DIALOG_MODELESS  <br/> |0x0000000C  <br/> |此值可以传递给 _ulFlags_ 参数中的简单 MAPI MAPISendMail 函数，以指定由默认邮件应用程序显示无模式对话框。 如果此标记和 MAPI_DIALOG (0x00000008) 均未设置，将不会显示对话框。  <br/> |
|MAPI_NO_CACHE  <br/> |0x00000200  <br/> |如果 Microsoft Office Outlook 处于缓存 Exchange 模式且在缓存模式中打开了一个存储区，客户端或服务提供商可以调用 [IMsgStore::OpenEntry](imsgstore-openentry.md)，设置 _ulFlags_ 参数的 **MAPI_NO_CACHE** 标记，以便在远程存储区上打开某个项目或文件夹。 请注意，如果在远程服务器上使用 **MDB_ONLINE** 标记打开邮件存储区，则无需使用 **MAPI_NO_CACHE** 标记。  <br/> |
|MAPI_UNICODE  <br/> |0x80000000  <br/> |客户端或服务提供商可以调用 [OpenIMsgOnIStg](openimsgonistg.md) 函数，设置 _ulFlags_ 参数中的 **MAPI_UNICODE** 标记，来创建 Unicode.msg 文件。 生成的 [IMessage: IMAPIProp](imessageimapiprop.md) 文件显示 **STORE_UNICODE_OK** 位于其 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中，且支持 Unicode 属性。 此常量在 mapidefs.h 中定义。  <br/> |
|MDB_ONLINE  <br/> |0x00000100  <br/> |如果 Outlook 处于缓存 Exchange 模式，客户端或服务提供商可以调用 [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) 方法，设置 _ulFlags_ 参数中的 **MDB_ONLINE** 标记，以覆盖与本地邮件存储区的连接，并打开远程服务器上的存储区。 请注意，不能在同一个 MAPI 会话中同时在缓存模式和非缓存模式下打开 Exchange 存储。 如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。  <br/> |
|NON_EMS_XP_SAVE  <br/> |0x00001000  <br/> |客户端可以调用 [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法，设置 _ulFlags_ 参数中的 **NON_EMS_XP_SAVE** 标记，以指示未从 Exchange 服务器传送邮件。 应将此标记与 _ulFlags_ 参数中的 **ITEMPROC_FORCE** 标记结合使用，向 PST 存储区表明，在 PST 存储区通知任何侦听客户端有关邮件到达之前，邮件有资格进行规则处理。 此规则仅适用于在除 Exchange 服务器以外的服务器上使用 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 创建的新邮件（这种情况下 Exchange 服务器已处理邮件上的规则）。  <br/> |
|SPAMFILTER_ONSAVE  <br/> |0x00000080  <br/> |客户端可以调用 [IMAPIProp::SaveChanges](imapiprop-savechanges.md)，设置 _ulFlags_ 参数中的 **SPAMFILTER_ONSAVE** 标记，以便在正在保存的邮件上启用垃圾邮件筛选。 垃圾邮件筛选支持只有在发件人的电子邮件地址类型为简单邮件传输协议 (SMTP) 且正在将邮件保存到个人文件夹文件 (PST) 存储区的情况下可用。  <br/> |
|STORE_ITEMPROC  <br/> |0x00200000  <br/> |如果在包装的 PST 存储区的 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中设置此标记，它表示在新邮件到达存储区时，存储区会单独在邮件上处理规则和垃圾邮件。 存储区然后调用 [IMAPISupport::Notify](imapisupport-notify.md)，在[通知](notification.md)结构中设置作为参数传递的 **fnevNewMail**，并将新邮件的详细信息传递到侦听客户端。 随后，当侦听客户端收到通知，它不会处理邮件上的规则。  <br/> |
|STORE_UNICODE_OK  <br/> |0x00040000  <br/> |如果此标志包含在 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中，它表示存储支持 Unicode 存储。 客户端可以查找标记以决定是否请求或将 Unicode 信息保存到存储区。  <br/> |
   
### <a name="definitions-for-archiving-items-in-a-folder"></a>在文件夹中存档项目的定义

以下常量定义是用于设置 [PidTagAgingGranularity 规范属性](pidtagaginggranularity-canonical-property.md)的值。
  
```cpp
#define AG_MONTHS 0 
#define AG_WEEKS  1 
#define AG_DAYS   2 

```

### <a name="definitions-for-displaying-remote-objects"></a>显示远程对象的定义

以下常量和宏定义用于显示远程对象。 有关详细信息，请参阅 [PidTagDisplayTypeEx 规范属性](pidtagdisplaytypeex-canonical-property.md)。
  
```cpp
#define DTE_FLAG_REMOTE_VALID0x80000000 
#define DTE_FLAG_ACL_CAPABLE    0x40000000 
#define DTE_MASK_REMOTE        0x0000ff00 
#define DTE_MASK_LOCAL        0x000000ff 
  
#define DTE_IS_REMOTE_VALID(v)(!!((v) & DTE_FLAG_REMOTE_VALID)) 
#define DTE_IS_ACL_CAPABLE(v)(!!((v) & DTE_FLAG_ACL_CAPABLE)) 
#define DTE_REMOTE(v)(((v) & DTE_MASK_REMOTE) >> 8) 
#define DTE_LOCAL(v)((v) & DTE_MASK_LOCAL) 
  
#define DT_ROOM((ULONG) 0x00000007) 
#define DT_EQUIPMENT((ULONG) 0x00000008) 
#define DT_SEC_DISTLIST((ULONG) 0x00000009)
```

### <a name="definitions-for-exchange-address-book-and-message-store-error-codes"></a>Exchange 通讯簿和邮件存储错误代码定义

下列包含 Exchange 通讯簿以及邮件存储的错误代码定义，它们具有重新连接功能。 对断开连接的全局编录 (GC) 的最后一次调用可能会导致 **MAPI_E_END_OF_SESSION** 错误，可能需要重试。 
  
Outlook 的 MAPI 支持重新连接到 GC 服务器，而不需要特殊的重新配置，但是一些其他错误代码可以返回给客户端。
  
||||
|:-----|:-----|:-----|
|MAPI_E_END_OF_SESSION  <br/> |0x80040200  <br/> |断开连接时返回。  <br/> |
|MAPI_E_RECONNECTED  <br/> |0x80040125  <br/> |在远程过程调用 (RPC) 连接令牌过期时返回。 如果当前事务的令牌不同于连接令牌，则意味着它已重新连接，因此将返回 **MAPI_E_RECONNECTED**，且可以作为相同的 **MAPI_E_END_OF_SESSION** 处理。 应重试调用。  <br/> |
|MAPI_E_OFFLINE  <br/> |0x80040126  <br/> |连接处于脱机状态时返回。 通常情况下，这意味着环境中出现了一些状况，比如服务器故障或网络连接丢失。 该错误最有可能在使用缓存模式配置文件和尝试绕过缓存与服务器通信时发生。 如果缓存无法初始建立到服务器的连接，它可能处于脱机状态，其中可能会显示 **MAPI_E_OFFLINE**。  <br/> |
   
在所有可能出现的场景中，前两个错误都不会返回。 大多数情况下，将返回 **MAPI\_E_NETWORK_ERROR** 或 **MAPI_E_CALL_FAILED**。 使用 [Microsoft Exchange Server MAPI 客户端和协作数据对象 1.2.1](https://support.microsoft.com/kb/171440) 下载，两种错误都不会出现。 
  
### <a name="definitions-for-exchange-server-mailbox-cached-mode-quotas"></a>Exchange 服务器邮箱缓存模式配额的定义

Microsoft Outlook 2010 和 Microsoft Outlook 2013 使用以下常量定义来设置 Exchange 缓存模式配置文件配额，该配额等同于 Exchange 邮箱配额，只不过只有在使用联机配置文件时才提供。
  
```cpp
#define PR_QUOTA_WARNING PROP_TAG( PT_LONG, 0x341A)
#define PR_QUOTA_SEND    PROP_TAG( PT_LONG, 0x341B)
#define PR_QUOTA_RECEIVE PROP_TAG( PT_LONG, 0x341C)
```

这些属性映射到其对应的联机属性并包含以千字节为单位的相同值。 PR_QUOTA_WARNING 映射到 PR_STORAGE_QUOTA_LIMIT，PR_QUOTA_SEND 映射到 PR_QUOTA_PROHIBIT_SEND_QUOTA，以及 PR_QUOTA_RECEIVE 映射到 PR_PROHIBIT_RECEIVE_QUOTA。
  
### <a name="definitions-for-message-format"></a>邮件格式定义

以下常量定义是用于设置 [PidTagMessageEditorFormat 规范属性](pidtagmessageeditorformat-canonical-property.md)的值。
  
```cpp
#define EDITOR_FORMAT_DONTKNOW  ((ULONG) 0) 
#define EDITOR_FORMAT_PLAINTEXT ((ULONG) 1) 
#define EDITOR_FORMAT_HTML      ((ULONG) 2) 
#define EDITOR_FORMAT_RTF       ((ULONG) 3)
```

### <a name="definitions-for-using-rpc-over-http"></a>通过 HTTP 使用 RPC 的定义

有关用作标记来设置属性的常量定义，请参阅 [PidTagRpcOverHttpFlags 规范属性](pidtagrpcoverhttpflags-canonical-property.md)主题。 
  
有关用于设置属性的常量定义，请参阅 [PidTagRpcOverHttpProxyAuthScheme 规范属性](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)主题。 
  
### <a name="identifiers"></a>标识符

使用在 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 `DEFINE_OLEGUID` 宏，将以下 GUID 符号名称与其值关联起来。 
  
```cpp
//{0002038A-0000-0000-C000-000000000046}
#if !defined(INITGUID) || defined(USES_IID_IMessageRaw) 
DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0); 
#endif
```

下列标识符用于通讯簿的 Capone 配置文件部分，它支持多个 Exchange ([MultiEx](using-multiple-exchange-accounts.md)) 邮箱，包含一个 [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) 属性，以便有效地关闭由 [SetDefaultDir](iaddrbook-setdefaultdir.md) 指定的默认容器。
  
```cpp
// {00020D0A-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_CAPONE_PROF, 0x00020d0a, 0, 0);
```

### <a name="interface-identifiers"></a>接口标识符

#### <a name="imapisync"></a>IMAPISync
  
```cpp
DEFINE_GUID(IID_IMAPISync, 0x5024a385, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);

```

#### <a name="imapisyncprogresscallback"></a>IMAPISyncProgressCallback
  
```cpp
DEFINE_GUID(IID_IMAPISyncProgressCallback, 0x5024a386, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);
```

#### <a name="iidicontabadmin"></a>IID_IContabAdmin
  
```cpp
// {CC6A3BA9-E7F5-4769-887B-34E190817BFC}
DEFINE_GUID(IID_IContabAdmin, 0xcc6a3ba9, 0xe7f5, 0x4769, 0x88, 0x7b, 0x34, 0xe1, 0x90, 0x81, 0x7b, 0xfc);

```

#### <a name="iidimapisecuremessage"></a>IID_IMAPISECUREMESSAGE
  
```cpp
DEFINE_GUID(IID_IMAPISecureMessage, 0x253cc320, 0xeab6, 0x11d0, 0x82, 0x22, 0, 0x60, 0x97, 0x93, 0x87, 0xea);

```

#### <a name="iidimapigetsession"></a>IID_IMAPIGetSession
  
```cpp
DEFINE_GUID(IID_IMAPIGetSession, 0x614ab435, 0x491d, 0x4f5b, 0xa8, 0xb4, 0x60, 0xeb, 0x3, 0x10, 0x30, 0xc6);

```

### <a name="pst-override-handler-interface-identifiers"></a>PST 重写处理程序接口标识符

#### <a name="iidipstoverridereq"></a>IID_IPSTOVERRIDEREQ
  
```cpp
// {892EBC6D-24DC-4d90-BA48-C6CBEC14A86A}
DEFINE_GUID(IID_IPSTOVERRIDEREQ, 0x892ebc6d, 0x24dc, 0x4d90, 0xba, 0x48, 0xc6, 0xcb, 0xec, 0x14, 0xa8, 0x6a);
```

#### <a name="iidipstoverride1"></a>IID_IPSTOVERRIDE1
  
```cpp
// {FBB68D34-F561-44fb-A8CA-AE36696342CA}
DEFINE_GUID(IID_IPSTOVERRIDE1, 0xfbb68d34, 0xf561, 0x44fb, 0xa8, 0xca, 0xae, 0x36, 0x69, 0x63, 0x42, 0xca);
```

## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [关于 Outlook 使用的命名属性](about-named-properties-used-by-outlook.md)
- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

