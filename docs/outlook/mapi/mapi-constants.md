---
title: MAPI 常量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8fa5ac8d-3f63-499c-bb4e-439984773e4a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d6d6c55776c1379ec1dab0e9a6f7ef0943d2480e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776219"
---
# <a name="mapi-constants"></a>MAPI 常量

**适用于**： Outlook 
  
本主题包含常量定义、 MAPI 接口声明和 MAPI Api 使用的类和接口标识符。
  
## <a name="class-and-interface-identifiers"></a>类和接口标识符

使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 的符号名称相关联的值，除非另有说明。
  
## <a name="attachment-security-conversion-api"></a>附件安全转换 API

此部分包含附件安全 api 常量定义和界面标识符。
  
```cpp
// {b2533636-c3f3-416f-bf04-aefe41abaae2}
DEFINE_GUID(IID_IAttachmentSecurity, 0xb2533636, 0xc3f3, 0x416f, 0xbf, 0x04, 0xae, 0xfe, 0x41, 0xab, 0xaa, 0xe2);
```

使用 Windows SDK 标头文件 mapidefs.h 中定义的 MAPIMETHOD 宏定义纯虚函数**[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**。 
  
```cpp
#define MAPI_IATTACHMENTSECURITY_METHODS(IPURE)         MAPIMETHOD(IsAttachmentBlocked)         (LPCWSTR pwszFileName, BOOL *pfBlocked) IPURE;
```

使用 Windows SDK 标头文件 mapidefs.h 中定义 DECLARE_MAPI_INTERFACE_ 宏以定义**[IAttachmentSecurity](iattachmentsecurityiunknown.md)** 虚拟方法表。 
  
```cpp
DECLARE_MAPI_INTERFACE_(IAttachmentSecurity, IUnknown) 
{ 
    BEGIN_INTERFACE 
    MAPI_IUNKNOWN_METHODS(PURE) 
    MAPI_IATTACHMENTSECURITY_METHODS(PURE) 
};
```

## <a name="mapi-mime-conversion-api"></a>MAPI MIME 转换 API

本节包含对 MAPI MIME 转换 API 常量定义和类和接口标识符。
  
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
|E_INVALIDARG  <br/> | *Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义*  <br/> |
   
### <a name="class-identifiers"></a>类标识符

```cpp
// {4e3a7680-b77a-11d0-9da5-00c04fd65685}
DEFINE_GUID(CLSID_IConverterSession, 0x4e3a7680, 0xb77a, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

### <a name="interface-identifiers"></a>界面标识符

```cpp
// {4b401570-b77b-11d0-9da5-00c04fd65685}
DEFINE_GUID(IID_IConverterSession, 0x4b401570, 0xb77b, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

## <a name="offline-state-api"></a>脱机状态 API

此部分包含脱机状态 api 常量定义和类和接口标识符。
  
### <a name="constants"></a>常量

|||
|:-----|:-----|
|E_INVALIDARG  <br/> | *Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义*  <br/> |
|E_NOINTERFACE  <br/> | *在 Windows (SDK) 标头文件 winerror.h 中定义*  <br/> |
|MAPIOFFLINE_ADVISE_DEFAULT  <br/> |满足） 0  <br/> |
|MAPIOFFLINE_UNADVISE_DEFAULT  <br/> |满足） 0  <br/> |
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

### <a name="interface-identifiers"></a>界面标识符

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

此部分包含常量定义的命名属性的命名空间引用和其他相关的常量。
  
### <a name="definitions-for-named-properties"></a>定义命名属性

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

### <a name="definitions-for-namespaces"></a>定义命名空间

以下全局唯一标识符 (Guid) 表示的命名属性的命名空间。
  
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

请参阅 PSETID 定义的 MAPI 存储一节。
  
### <a name="other-constants"></a>其他常量

|||
|:-----|:-----|
|INSP_ONEOFFFLAGS  <br/> |0xD000000  <br/> |
|INSP_PROPDEFINITION  <br/> |0x2000000  <br/> |
|MNID_ID  <br/> | *标头文件 mapidefs.h 中定义。*  <br/> |
|MNID_STRING  <br/> | *标头文件 mapidefs.h 中定义。*  <br/> |
|mtgNone  <br/> |0x0  <br/> |
|mtgRequest  <br/> |0x00000001  <br/> |
|mtgFullUpdate  <br/> |0x00010000  <br/> |
|mtgInfoUpdate  <br/> |0x00020000  <br/> |
|mtgOutofDate  <br/> |0x00080000  <br/> |
|mtgDelegated  <br/> |0x00100000  <br/> |
   
## <a name="replication-api"></a>复制 API

此部分包含有关复制 API 常量定义、 MAPI 接口声明和类和接口标识符。
  
### <a name="constants"></a>常量

以下是标识 MAPI 服务提供商[MAPIUID](mapiuid.md)结构： 
  
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
|MDB_OST_LOGON_UNICODE  <br/> |（满足） 0X00000800）  <br/> |
|MDB_OST_LOGON_ANSI  <br/> |（满足） 0X00001000）  <br/> |
|SHOW_SOFT_DELETES  <br/> |（满足） 0X00000002:UC）  <br/> |
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

### <a name="interface-identifiers"></a>界面标识符

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

使用与[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、 [IMAPISession::OpenEntry](imapisession-openentry.md)或[IMsgStore::OpenEntry](imsgstore-openentry.md)两个以下接口标识符打开，并分别忽略 folder 对象和 message 对象，任何提供程序检查。 
  
```cpp
//{57D333A0-F589-4b23-A3F9-85F82FEC153C}
DEFINE_GUID (IID_IMAPIFolderNoProvChk, 0x57D333A0, 0xF589, 0x4b23, 0xA3, 0xF9, 0x85, 0xF8, 0x2F, 0xEC, 0x15, 0x3C)
```

```cpp
//{C3505457-7B2E-4c3b-A8D6-6DD949BB97A1}
DEFINE_GUID (IID_IMessageNoProvChk, 0xC3505457, 0x7B2E, 0x4c3b, 0xA8, 0xD6, 0x6D, 0xD9, 0x49, 0xBB, 0x97, 0xA1)
```

## <a name="mapi-store"></a>MAPI 存储区

本节包含的常量定义和界面标识符由 Api 该接口与 MAPI 存储。
  
### <a name="constants"></a>常量

||||
|:-----|:-----|:-----|
|fnevIndexing  <br/> |（满足） 0X00010000）  <br/> |存储提供程序可以指定**fnevIndexing**中的**[通知](notification.md)** 结构**ulEventType**成员，才能通知索引器对象是供索引。 **通知**结构的**信息**成员包含**[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。  <br/> |
|FS_NONE  <br/> |0x00  <br/> |客户端可以对返回的位掩码调用**[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** 并检查。 **FS_NONE**指示该文件夹不支持共享。  <br/> |
|FS_SUPPORTS_SHARING  <br/> |0x01  <br/> |客户端可以对返回的位掩码调用**IFolderSupport::GetSupportMask**并检查。 **FS_SUPPORTS_SHARING**指示文件夹支持共享。  <br/> |
|INDEXING_SEARCH_OWNER  <br/> |（满足） 0X00000001）  <br/> |标识向索引器对象是供索引推送通知的进程。  <br/> |
|MNID_ID  <br/> |Microsoft Windows 软件开发工具包 (SDK) 标头文件 mapidefs.h 中定义  <br/> |一个**[MAPINAMEID](mapinameid.md)** 结构的**ulKind**字段的值。  <br/> |
|MNID_STRING  <br/> |Microsoft Windows 软件开发工具包 (SDK) 标头文件 mapidefs.h 中定义。  <br/> |一个**[MAPINAMEID](mapinameid.md)** 结构的**ulKind**字段的值。  <br/> |
|MSCAP_RES_ANNOTATION  <br/> |（满足） 0X00000001）  <br/> |如果客户端指定**MSCAP_SEL_RESTRICTION** *mscapSelector* **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)**， **GetCapabilities**可以返回此值，如果存储忽略限制中的参数无效。  <br/> |
|MSCAP_SECURE_FOLDER_HOMEPAGES  <br/> |（满足） 0X00000020）  <br/> |如果客户端指定**MSCAP_SEL_FOLDER** *mscapSelector* **IMSCapabilities::GetCapabilities**， **GetCapabilities**可以返回此值，如果存储是支持文件夹主页的非默认存储区。  <br/> |
|STORE_PUSHER_OK  <br/> |（满足） 0X00800000）  <br/> |客户端可以获取**[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 来确定邮件存储的特征的属性。 如果存储提供程序中的位掩码，是指 MAPI 协议处理程序将不存储进行爬网设置**STORE_PUSHER_OK**标志以及存储负责通过通知的任何更改推送到索引器已编制索引的邮件。  <br/> |
   
### <a name="definitions-for-namespaces"></a>定义命名空间

以下全局唯一标识符 (Guid) 表示命名属性的命名的空间。 他们编制索引的 MAPI 协议处理程序 (PH) 中，并以只读方式记录。
  
> [!CAUTION]
> 不应使用的命名的属性创建或修改的项目。 
  
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

#### <a name="mnidid-properties"></a>MNID_ID 属性
  
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

#### <a name="mnidstring-properties"></a>MNID_STRING 属性
  
```cpp
// In PS_PUBLIC_STRINGS 
"Keywords"
```

```cpp
// In PS_INTERNET_HEADERS
"return-path"
```

### <a name="interface-identifiers"></a>界面标识符

```cpp
//{00375ac3-ecaf-4ef8-a527-34f452fa9c67}
DEFINE_GUID(IID_IFolderSupport, 0x00375ac3, 0xecaf, 0x4ef8, 0xa5, 0x27, 0x34, 0xf4, 0x52, 0xfa, 0x9c, 0x67);

```

```cpp
//{29F3AB10-554d-11d0-a97c-00a0c911f50a}
#define DEFINE_PRXGUID(_name, _l) DEFINE_GUID(_name, (0x29f3ab10 + _l), 0x554d, 0x11d0, 0xa9, 0x7c, 0x00, 0xa0, 0xc9, 0x11, 0xf5, 0x0a) 
DEFINE_PRXGUID(IID_IProxyStoreObject, 0x00000000L);
```

使用`DEFINE_OLEGUID`其值与关联的以下 GUID 符号名称 Windows SDK 标头文件 guiddef.h 中定义的宏。 
  
```cpp
//{00020393-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_IMSCapabilities, 0x00020393, 0, 0)

```

## <a name="mapi-address-book-constants"></a>MAPI 通讯簿常量

此部分包含常量定义的 MAPI 通讯簿。
  
### <a name="constants"></a>常量

||||
|:-----|:-----|:-----|
|CONTAB_ROOT  <br/> |（满足） 0X00000001）  <br/> |MAPI 通讯簿对象的的根文件夹。  <br/> |
|CONTAB_SUBROOT  <br/> |（满足） 0X00000002:UC）  <br/> |MAPI 通讯簿对象的根文件夹中包含子文件夹。  <br/> |
|CONTAB_CONTAINER  <br/> |（满足） 0X00000003）  <br/> |通讯簿容器对象。  <br/> |
|CONTAB_USER  <br/> |（满足） 0X00000004）  <br/> |消息的用户对象。  <br/> |
|CONTAB_DISTLIST  <br/> |（满足） 0X00000005）  <br/> |通讯组列表对象。  <br/> |
   
## <a name="additional-mapi-constants"></a>其他 MAPI 常量

此部分包含包括错误代码和界面标识符的以前没有公开并记录了 MAPI Api 使用的常量定义。
  
||||
|:-----|:-----|:-----|
|DIALOG_MODAL  <br/> |（满足） 0X00000001）  <br/> |当客户端调用[IAddrBook::Details](iaddrbook-details.md)方法时，则客户端必须在_ulFlags_参数来显示模式对话框显示有关特定通讯簿条目的详细信息设置**DIALOG_MODAL**标志。 此常量 mapidefs.h 中定义。  <br/> |
|ITEMPROC_FORCE  <br/> |0x00000800  <br/> |在 Outlook 2007 中，换行的 PST 存储有规则垃圾邮件筛选在和处理新邮件通知新消息的 MAPI 客户端之前。 提供程序或使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法在 PST 存储中创建一个新的邮件客户端应[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以指示到 PST 的_ulFlags_参数中设置**ITEMPROC_FORCE**标志存储邮件符合条件的规则处理之前存储通知新消息的到达任何侦听客户端。 请注意，仅处理此类规则适用于新邮件不是 Microsoft Exchange Server，服务器上创建，因为 Exchange 服务器处理的服务器上的邮件的规则。 因此提供程序或创建邮件客户端必须通过此标志与**NON_EMS_XP_SAVE**，这表明服务器不是 Exchange server 结合使用。  <br/> |
| MAPI_BG_SESSION  <br/> |0x00200000  <br/> |客户端可以调用[MAPILogonEx](mapilogonex.md)函数中，登录到会话，并执行任何操作在后台_flFlags_参数中设置**MAPI_BG_SESSION**标志。 一般来说，如果打算执行后台线程上或在单独的进程中不到前台线程引人注目的方式处理客户端，它应与**MAPI_BG_SESSION**标志调用[MAPILogonEx](mapilogonex.md) 。 使用此示例是一个客户端应用程序，如索引引擎，打开背景类型访问个人文件夹文件 (PST)。  <br/> |
|MAPI_CACHE_ONLY  <br/> |0x00004000  <br/> |客户端可以调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)方法，将**MAPI_CACHE_ONLY**标志设置_ulFlags_参数可打开的通讯簿条目并可访问该随后仅从缓存中。 使用此示例是想要在缓存 Exchange 模式下打开全局地址列表和从缓存中访问该通讯簿中的条目，而不创建客户端和服务器之间的通信客户端应用程序。  <br/> |
|MAPI_DIALOG_MODELESS  <br/> |0x0000000C  <br/> |此值传递给使用_ulFlags_参数指定将无模式对话框显示默认邮件应用程序中的简单 MAPI MAPISendMail 函数。 如果设置此标志和 MAPI_DIALOG (0x00000008) 都不被不显示任何对话框。  <br/> |
|MAPI_NO_CACHE  <br/> |0x00000200  <br/> |如果是在缓存 Exchange 模式下的 Microsoft Office Outlook 和存储区中缓存模式已打开，客户端或服务提供程序可以呼叫[IMsgStore::OpenEntry](imsgstore-openentry.md)， _ulFlags_参数打开一个项目中设置**MAPI_NO_CACHE**标志或远程存储的文件夹。 请注意，是否您使用**MDB_ONLINE**标志远程服务器上打开的消息存储，不需要使用**MAPI_NO_CACHE**标志。  <br/> |
|MAPI_UNICODE  <br/> |0x80000000  <br/> |客户端或服务提供程序可以调用[OpenIMsgOnIStg](openimsgonistg.md)函数， _ulFlags_参数创建 Unicode.msg 文件中设置**MAPI_UNICODE**标志。 产生的[IMessage: IMAPIProp](imessageimapiprop.md)文件中其[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)显示**STORE_UNICODE_OK**且支持 Unicode 属性。 此常量 mapidefs.h 中定义。  <br/> |
|MDB_ONLINE  <br/> |0x00000100  <br/> |如果 Outlook 为缓存 Exchange 模式下，客户端或服务提供程序可以调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法， _ulFlags_参数覆盖本地消息存储库的连接并打开中设置**MDB_ONLINE**标志远程服务器上存储。 请注意，您不能打开 Exchange 存储在缓存模式和非缓存模式下在同一 MAPI 会话中的同一时间。 如果您已经打开的缓存的消息存储之前，必须也关闭存储打开与此标志，或打开新其中可以使用此标志打开 Exchange 存储的远程服务器上的 MAPI 会话。  <br/> |
|NON_EMS_XP_SAVE  <br/> |0x00001000  <br/> |客户端可以调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，将**NON_EMS_XP_SAVE**标志设置_ulFlags_参数来指示邮件尚未传递从 Exchange 服务器中。 此标志应该用于结合使用_ulFlags_参数中的**ITEMPROC_FORCE**标志指示邮件是适合规则处理之前 PST PST 存储通知的到达任何侦听客户端消息。 此规则处理仅适用于在不是 Exchange 服务器 （在这种情况下 Exchange 服务器会已经处理邮件的规则） 的服务器创建与[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)的新邮件。  <br/> |
|SPAMFILTER_ONSAVE  <br/> |0x00000080  <br/> |客户端可以调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)，在要启用垃圾邮件筛选上一条消息，正在保存的_ulFlags_参数中设置**SPAMFILTER_ONSAVE**标志。 只有当发件人的电子邮件地址类型为简单邮件传输协议 (SMTP)，并且将存储个人文件夹文件 (PST) 用于保存邮件的垃圾邮件筛选支持可用。  <br/> |
|STORE_ITEMPROC  <br/> |0x00200000  <br/> |如果换行 PST 存储[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中设置此标志，则表示当新邮件到达存储，存储的规则，并且垃圾邮件筛选单独对邮件处理。 存储然后调用[IMAPISupport::Notify](imapisupport-notify.md)，设置**fnevNewMail**中作为参数，传递的[通知](notification.md)结构并将新消息的详细信息传递给侦听的客户端。 随后，侦听客户端接收通知时，它不处理邮件的规则。  <br/> |
|STORE_UNICODE_OK  <br/> |0x00040000  <br/> |如果此标志包括在[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)，它指示的存储支持 Unicode 存储。 客户端可以查看此标志以确定是请求还是将 Unicode 信息保存到存储的状态。  <br/> |
   
### <a name="definitions-for-archiving-items-in-a-folder"></a>定义存档文件夹中的项目

以下常量定义是用于设置[PidTagAgingGranularity 规范属性](pidtagaginggranularity-canonical-property.md)的值。
  
```cpp
#define AG_MONTHS 0 
#define AG_WEEKS  1 
#define AG_DAYS   2 

```

### <a name="definitions-for-displaying-remote-objects"></a>定义用于显示远程对象

以下常量和宏定义所显示远程对象。 有关详细信息，请参阅[PidTagDisplayTypeEx 规范属性](pidtagdisplaytypeex-canonical-property.md)。
  
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

### <a name="definitions-for-exchange-address-book-and-message-store-error-codes"></a>定义 Exchange 通讯簿和邮件存储错误代码

以下包含具有重新连接功能的 Exchange 通讯簿和邮件存储的错误代码定义。 向已断开连接全局编录 (GC) 的最后一个呼叫可能会导致**MAPI_E_END_OF_SESSION**错误，需要重试。 
  
Outlook 的 MAPI 支持重新连接到 GC 服务器没有特殊重新配置，但其他一些错误代码返回客户端。
  
||||
|:-----|:-----|:-----|
|MAPI_E_END_OF_SESSION  <br/> |0x80040200  <br/> |返回时已断开连接。  <br/> |
|MAPI_E_RECONNECTED  <br/> |0x80040125  <br/> |远程过程调用 (RPC) 连接令牌已过期时返回。 如果当前事务的令牌不同的连接的意味着它的令牌已重新连接，因此**MAPI_E_RECONNECTED**返回，并且可以是相同视为**MAPI_E_END_OF_SESSION**。 应重试呼叫。  <br/> |
|MAPI_E_OFFLINE  <br/> |0x80040126  <br/> |返回当连接处于脱机状态。 通常，这意味着事物发生在环境中，例如服务器故障或丢失网络连接。 此错误是最有可能发生时使用缓存的模式配置文件和尝试绕过缓存与服务器进行通信。 如果缓存从不能够最初建立与服务器的连接，则它可能处于脱机状态**MAPI_E_OFFLINE**无法显示顺序。  <br/> |
   
都不上述两个错误将返回所有方案中，它们将可能出现应用。 在大多数情况下， **MAPI\_E_NETWORK_ERROR**或将返回**MAPI_E_CALL_FAILED** 。 都不会使用[Microsoft Exchange Server MAPI 客户端和协作数据对象 1.2.1 （英文）](http://support.microsoft.com/kb/171440)下载。 
  
### <a name="definitions-for-exchange-server-mailbox-cached-mode-quotas"></a>Exchange Server 邮箱定义缓存模式配额

以下常量定义使用 Microsoft Outlook 2010 和 Microsoft Outlook 2013 设置 Exchange 缓存等同于否则为仅与联机配置可用的 Exchange 邮箱配额的模式配置文件配额。
  
```cpp
#define PR_QUOTA_WARNING PROP_TAG( PT_LONG, 0x341A)
#define PR_QUOTA_SEND    PROP_TAG( PT_LONG, 0x341B)
#define PR_QUOTA_RECEIVE PROP_TAG( PT_LONG, 0x341C)
```

这些属性映射到其相对应的联机属性，并包含相同的值为千字节。 PR_QUOTA_WARNING 映射到 PR_STORAGE_QUOTA_LIMIT，PR_QUOTA_SEND 到 PR_QUOTA_PROHIBIT_SEND_QUOTA，并为 PR_PROHIBIT_RECEIVE_QUOTA PR_QUOTA_RECEIVE。
  
### <a name="definitions-for-message-format"></a>定义邮件格式

以下常量定义是用于设置[PidTagMessageEditorFormat 规范属性](pidtagmessageeditorformat-canonical-property.md)的值。
  
```cpp
#define EDITOR_FORMAT_DONTKNOW  ((ULONG) 0) 
#define EDITOR_FORMAT_PLAINTEXT ((ULONG) 1) 
#define EDITOR_FORMAT_HTML      ((ULONG) 2) 
#define EDITOR_FORMAT_RTF       ((ULONG) 3)
```

### <a name="definitions-for-using-rpc-over-http"></a>使用 RPC over HTTP 的定义

请参阅用作标志将属性设置的常量定义的[PidTagRpcOverHttpFlags 规范属性](pidtagrpcoverhttpflags-canonical-property.md)主题。 
  
请参阅用于将属性设置的常量定义的[PidTagRpcOverHttpProxyAuthScheme 规范属性](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)主题。 
  
### <a name="identifiers"></a>标识符

使用`DEFINE_OLEGUID`Microsoft Windows 软件开发工具包 (SDK) 的标头文件 guiddef.h，将以下 GUID 符号名称相关联的值中定义的宏。 
  
```cpp
//{0002038A-0000-0000-C000-000000000046}
#if !defined(INITGUID) || defined(USES_IID_IMessageRaw) 
DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0); 
#endif
```

下列标识符是通讯簿，它支持多个 Exchange ([MultiEx](using-multiple-exchange-accounts.md)) 邮箱中包含的[PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性的有效地关闭默认 Capone 配置文件一节指定[SetDefaultDir](iaddrbook-setdefaultdir.md)的容器。
  
```cpp
// {00020D0A-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_CAPONE_PROF, 0x00020d0a, 0, 0);
```

### <a name="interface-identifiers"></a>界面标识符

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

### <a name="pst-override-handler-interface-identifiers"></a>PST 重写处理程序界面标识符

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

