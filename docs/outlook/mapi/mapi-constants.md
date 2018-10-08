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
ms.openlocfilehash: dfc7d16cdb2f57d3f095ceea5fa1ba2eba2e3afe
ms.sourcegitcommit: b91294da1627f6580f52fd3867e2fec8073c6531
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2018
ms.locfileid: "25362041"
---
# <a name="mapi-constants"></a><span data-ttu-id="3f85c-103">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-103">MAPI Constants</span></span>

<span data-ttu-id="3f85c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f85c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f85c-105">本主题包含常量定义、MAPI 接口声明，以及 MAPI API 使用的类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-105">This topic contains constant definitions, MAPI interface declarations, and class and interface identifiers used by the MAPI APIs.</span></span>
  
## <a name="class-and-interface-identifiers"></a><span data-ttu-id="3f85c-106">类和接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-106">Class and interface identifiers</span></span>

<span data-ttu-id="3f85c-107">使用在 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_GUID 宏，将全局唯一标识符 (GUID) 符号名称与其值关联起来，除非另有说明。</span><span class="sxs-lookup"><span data-stu-id="3f85c-107">Use the DEFINE_GUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate globally unique identifier (GUID) symbolic names with their values, unless otherwise indicated.</span></span>
  
## <a name="attachment-security-conversion-api"></a><span data-ttu-id="3f85c-108">附件安全转换 API</span><span class="sxs-lookup"><span data-stu-id="3f85c-108">Attachment security conversion API</span></span>

<span data-ttu-id="3f85c-109">本部分包含常量定义和附件安全 API 的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-109">This section contains constant definitions and interface identifiers for the Attachment Security API.</span></span>
  
```cpp
// {b2533636-c3f3-416f-bf04-aefe41abaae2}
DEFINE_GUID(IID_IAttachmentSecurity, 0xb2533636, 0xc3f3, 0x416f, 0xbf, 0x04, 0xae, 0xfe, 0x41, 0xab, 0xaa, 0xe2);
```

<span data-ttu-id="3f85c-110">使用在 Windows SDK 头文件 mapidefs.h 中定义的 MAPIMETHOD 宏来定义纯虚函数 **[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**。</span><span class="sxs-lookup"><span data-stu-id="3f85c-110">Use the MAPIMETHOD macro defined in the Windows SDK header file mapidefs.h to define the pure virtual function **[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**.</span></span> 
  
```cpp
#define MAPI_IATTACHMENTSECURITY_METHODS(IPURE)         MAPIMETHOD(IsAttachmentBlocked)         (LPCWSTR pwszFileName, BOOL *pfBlocked) IPURE;
```

<span data-ttu-id="3f85c-111">使用在 Windows SDK 头文件 mapidefs.h 中定义的 DECLARE_MAPI_INTERFACE_ 宏来定义 **[IAttachmentSecurity](iattachmentsecurityiunknown.md)** 的虚拟方法表。</span><span class="sxs-lookup"><span data-stu-id="3f85c-111">Use the DECLARE_MAPI_INTERFACE_ macro defined in the Windows SDK header file mapidefs.h to define the virtual method table for **[IAttachmentSecurity](iattachmentsecurityiunknown.md)**.</span></span> 
  
```cpp
DECLARE_MAPI_INTERFACE_(IAttachmentSecurity, IUnknown) 
{ 
    BEGIN_INTERFACE 
    MAPI_IUNKNOWN_METHODS(PURE) 
    MAPI_IATTACHMENTSECURITY_METHODS(PURE) 
};
```

## <a name="mapi-mime-conversion-api"></a><span data-ttu-id="3f85c-112">MAPI-MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="3f85c-112">MAPI-MIME conversion API</span></span>

<span data-ttu-id="3f85c-113">本部分包含常量定义和 MAPI-MIME 转换 API 的类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-113">This section contains constant definitions and class and interface identifiers for the MAPI-MIME Conversion API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="3f85c-114">常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-114">Constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3f85c-115">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="3f85c-115">CCSF_SMTP</span></span>  <br/> |<span data-ttu-id="3f85c-116">0x0002</span><span class="sxs-lookup"><span data-stu-id="3f85c-116">0x0002</span></span>  <br/> |
|<span data-ttu-id="3f85c-117">CCSF_NOHEADERS</span><span class="sxs-lookup"><span data-stu-id="3f85c-117">CCSF_NOHEADERS</span></span>  <br/> |<span data-ttu-id="3f85c-118">0x0004</span><span class="sxs-lookup"><span data-stu-id="3f85c-118">0x0004</span></span>  <br/> |
|<span data-ttu-id="3f85c-119">CCSF_USE_TNEF</span><span class="sxs-lookup"><span data-stu-id="3f85c-119">CCSF_USE_TNEF</span></span>  <br/> | <span data-ttu-id="3f85c-120">0x0010</span><span class="sxs-lookup"><span data-stu-id="3f85c-120">0x0010</span></span>  <br/> |
|<span data-ttu-id="3f85c-121">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="3f85c-121">CCSF_INCLUDE_BCC</span></span>  <br/> |<span data-ttu-id="3f85c-122">0x0020</span><span class="sxs-lookup"><span data-stu-id="3f85c-122">0x0020</span></span>  <br/> |
|<span data-ttu-id="3f85c-123">CCSF_8BITHEADERS</span><span class="sxs-lookup"><span data-stu-id="3f85c-123">CCSF_8BITHEADERS</span></span>  <br/> | <span data-ttu-id="3f85c-124">0x0040</span><span class="sxs-lookup"><span data-stu-id="3f85c-124">0x0040</span></span>  <br/> |
|<span data-ttu-id="3f85c-125">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="3f85c-125">CCSF_USE_RTF</span></span>  <br/> |<span data-ttu-id="3f85c-126">0x0080</span><span class="sxs-lookup"><span data-stu-id="3f85c-126">0x0080</span></span>  <br/> |
|<span data-ttu-id="3f85c-127">CCSF_PLAIN_TEXT_ONLY</span><span class="sxs-lookup"><span data-stu-id="3f85c-127">CCSF_PLAIN_TEXT_ONLY</span></span>  <br/> |<span data-ttu-id="3f85c-128">0x1000</span><span class="sxs-lookup"><span data-stu-id="3f85c-128">0x1000</span></span>  <br/> |
|<span data-ttu-id="3f85c-129">CCSF_NO_MSGID</span><span class="sxs-lookup"><span data-stu-id="3f85c-129">CCSF_NO_MSGID</span></span>  <br/> |<span data-ttu-id="3f85c-130">0x4000</span><span class="sxs-lookup"><span data-stu-id="3f85c-130">0x4000</span></span>  <br/> |
|<span data-ttu-id="3f85c-131">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="3f85c-131">CCSF_GLOBAL_MESSAGE</span></span>  <br/> |<span data-ttu-id="3f85c-132">0x00200000</span><span class="sxs-lookup"><span data-stu-id="3f85c-132">0x00200000</span></span>  <br/> |
|<span data-ttu-id="3f85c-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3f85c-133">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="3f85c-134">*如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义*</span><span class="sxs-lookup"><span data-stu-id="3f85c-134">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h*</span></span>  <br/> |
   
### <a name="class-identifiers"></a><span data-ttu-id="3f85c-135">类标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-135">Class identifiers</span></span>

```cpp
// {4e3a7680-b77a-11d0-9da5-00c04fd65685}
DEFINE_GUID(CLSID_IConverterSession, 0x4e3a7680, 0xb77a, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

### <a name="interface-identifiers"></a><span data-ttu-id="3f85c-136">接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-136">Interface identifiers</span></span>

```cpp
// {4b401570-b77b-11d0-9da5-00c04fd65685}
DEFINE_GUID(IID_IConverterSession, 0x4b401570, 0xb77b, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

## <a name="offline-state-api"></a><span data-ttu-id="3f85c-137">脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="3f85c-137">About the Offline State API</span></span>

<span data-ttu-id="3f85c-138">本部分包含常量定义和脱机状态 API 的类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-138">This section contains constant definitions and class and interface identifiers for the Offline State API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="3f85c-139">常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-139">Constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3f85c-140">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3f85c-140">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="3f85c-141">*如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义*</span><span class="sxs-lookup"><span data-stu-id="3f85c-141">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h*</span></span>  <br/> |
|<span data-ttu-id="3f85c-142">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="3f85c-142">E_NOINTERFACE</span></span>  <br/> | <span data-ttu-id="3f85c-143">*如 Windows (SDK) 头文件 winerror.h 中所定义*</span><span class="sxs-lookup"><span data-stu-id="3f85c-143">*As defined in the Windows (SDK) header file winerror.h*</span></span>  <br/> |
|<span data-ttu-id="3f85c-144">MAPIOFFLINE_ADVISE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f85c-144">MAPIOFFLINE_ADVISE_DEFAULT</span></span>  <br/> |<span data-ttu-id="3f85c-145">(ULONG)0</span><span class="sxs-lookup"><span data-stu-id="3f85c-145">(ULONG)0</span></span>  <br/> |
|<span data-ttu-id="3f85c-146">MAPIOFFLINE_UNADVISE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f85c-146">MAPIOFFLINE_UNADVISE_DEFAULT</span></span>  <br/> |<span data-ttu-id="3f85c-147">(ULONG)0</span><span class="sxs-lookup"><span data-stu-id="3f85c-147">(ULONG)0</span></span>  <br/> |
|<span data-ttu-id="3f85c-148">MAPIOFFLINE_ADVISE_TYPE_STATECHANGE</span><span class="sxs-lookup"><span data-stu-id="3f85c-148">MAPIOFFLINE_ADVISE_TYPE_STATECHANGE</span></span>  <br/> |<span data-ttu-id="3f85c-149">1</span><span class="sxs-lookup"><span data-stu-id="3f85c-149">-1</span></span>  <br/> |
|<span data-ttu-id="3f85c-150">MAPIOFFLINE_CAPABILITY_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-150">MAPIOFFLINE_CAPABILITY_OFFLINE</span></span>  <br/> |<span data-ttu-id="3f85c-151">0x1</span><span class="sxs-lookup"><span data-stu-id="3f85c-151">0x1</span></span>  <br/> |
|<span data-ttu-id="3f85c-152">MAPIOFFLINE_CAPABILITY_ONLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-152">MAPIOFFLINE_CAPABILITY_ONLINE</span></span>  <br/> |<span data-ttu-id="3f85c-153">0x2</span><span class="sxs-lookup"><span data-stu-id="3f85c-153">0x2</span></span>  <br/> |
|<span data-ttu-id="3f85c-154">MAPIOFFLINE_FLAG_BLOCK</span><span class="sxs-lookup"><span data-stu-id="3f85c-154">MAPIOFFLINE_FLAG_BLOCK</span></span>  <br/> |<span data-ttu-id="3f85c-155">0x00002000</span><span class="sxs-lookup"><span data-stu-id="3f85c-155">0x00002000</span></span>  <br/> |
|<span data-ttu-id="3f85c-156">MAPIOFFLINE_FLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f85c-156">MAPIOFFLINE_FLAG_DEFAULT</span></span>  <br/> |<span data-ttu-id="3f85c-157">0x00000000</span><span class="sxs-lookup"><span data-stu-id="3f85c-157">0x00000000</span></span>  <br/> |
|<span data-ttu-id="3f85c-158">MAPIOFFLINE_STATE_ALL</span><span class="sxs-lookup"><span data-stu-id="3f85c-158">MAPIOFFLINE_STATE_ALL</span></span>  <br/> |<span data-ttu-id="3f85c-159">0x003f037f</span><span class="sxs-lookup"><span data-stu-id="3f85c-159">0x003f037f</span></span>  <br/> |
|<span data-ttu-id="3f85c-160">**联机或脱机**</span><span class="sxs-lookup"><span data-stu-id="3f85c-160">**Online or offline**</span></span> <br/> ||
|<span data-ttu-id="3f85c-161">MAPIOFFLINE_STATE_OFFLINE_MASK</span><span class="sxs-lookup"><span data-stu-id="3f85c-161">MAPIOFFLINE_STATE_OFFLINE_MASK</span></span>  <br/> |<span data-ttu-id="3f85c-162">0x00000003</span><span class="sxs-lookup"><span data-stu-id="3f85c-162">0x00000003</span></span>  <br/> |
|<span data-ttu-id="3f85c-163">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-163">MAPIOFFLINE_STATE_OFFLINE</span></span>  <br/> |<span data-ttu-id="3f85c-164">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-164">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-165">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-165">MAPIOFFLINE_STATE_ONLINE</span></span>  <br/> |<span data-ttu-id="3f85c-166">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-166">0x00000002</span></span>  <br/> |
   
### <a name="class-identifiers"></a><span data-ttu-id="3f85c-167">类标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-167">Class identifiers</span></span>

```cpp
//{fbeffd93-b11f-4094-842b-96dcd31e63d1}
DEFINE_GUID(GUID_GlobalState, 0xfbeffd93, 0xb11f, 0x4094, 0x84, 0x2b, 0x96, 0xdc, 0xd3, 0x1e, 0x63, 0xd1);
```

### <a name="interface-identifiers"></a><span data-ttu-id="3f85c-168">接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-168">Interface identifiers</span></span>

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

## <a name="outlook-named-properties"></a><span data-ttu-id="3f85c-169">Outlook 命名属性</span><span class="sxs-lookup"><span data-stu-id="3f85c-169">Outlook named properties</span></span>

<span data-ttu-id="3f85c-170">本部分包含命名属性的常量定义及其命名空间和其他相关常量。</span><span class="sxs-lookup"><span data-stu-id="3f85c-170">This section contains constant definitions for named properties and their namespaces, and other related constants.</span></span>
  
### <a name="definitions-for-named-properties"></a><span data-ttu-id="3f85c-171">命名属性定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-171">Definitions for named properties</span></span>

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

### <a name="definitions-for-namespaces"></a><span data-ttu-id="3f85c-172">命名空间定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-172">Definitions for namespaces</span></span>

<span data-ttu-id="3f85c-173">以下全局唯一标识符 (GUID) 代表命名属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f85c-173">The following globally unique identifiers (GUIDs) represent the namespaces of the named properties.</span></span>
  
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

<span data-ttu-id="3f85c-174">参考 PSETID 定义的 MAPI 存储部分。</span><span class="sxs-lookup"><span data-stu-id="3f85c-174">Refer to the section MAPI Store for the PSETID definitions.</span></span>
  
### <a name="other-constants"></a><span data-ttu-id="3f85c-175">其他常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-175">Other constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3f85c-176">INSP_ONEOFFFLAGS</span><span class="sxs-lookup"><span data-stu-id="3f85c-176">INSP_ONEOFFFLAGS</span></span>  <br/> |<span data-ttu-id="3f85c-177">0xD000000</span><span class="sxs-lookup"><span data-stu-id="3f85c-177">0xD000000</span></span>  <br/> |
|<span data-ttu-id="3f85c-178">INSP_PROPDEFINITION</span><span class="sxs-lookup"><span data-stu-id="3f85c-178">INSP_PROPDEFINITION</span></span>  <br/> |<span data-ttu-id="3f85c-179">0x2000000</span><span class="sxs-lookup"><span data-stu-id="3f85c-179">0x2000000</span></span>  <br/> |
|<span data-ttu-id="3f85c-180">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="3f85c-180">MNID_ID</span></span>  <br/> | <span data-ttu-id="3f85c-181">*如头文件 mapidefs.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="3f85c-181">*As defined in the header file mapidefs.h.*</span></span>  <br/> |
|<span data-ttu-id="3f85c-182">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="3f85c-182">MNID_STRING</span></span>  <br/> | <span data-ttu-id="3f85c-183">*如头文件 mapidefs.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="3f85c-183">*As defined in the header file mapidefs.h.*</span></span>  <br/> |
|<span data-ttu-id="3f85c-184">mtgNone</span><span class="sxs-lookup"><span data-stu-id="3f85c-184">mtgNone</span></span>  <br/> |<span data-ttu-id="3f85c-185">0x0</span><span class="sxs-lookup"><span data-stu-id="3f85c-185">0x0</span></span>  <br/> |
|<span data-ttu-id="3f85c-186">mtgRequest</span><span class="sxs-lookup"><span data-stu-id="3f85c-186">mtgRequest</span></span>  <br/> |<span data-ttu-id="3f85c-187">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-187">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-188">mtgFullUpdate</span><span class="sxs-lookup"><span data-stu-id="3f85c-188">mtgFullUpdate</span></span>  <br/> |<span data-ttu-id="3f85c-189">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-189">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-190">mtgInfoUpdate</span><span class="sxs-lookup"><span data-stu-id="3f85c-190">mtgInfoUpdate</span></span>  <br/> |<span data-ttu-id="3f85c-191">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-191">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-192">mtgOutofDate</span><span class="sxs-lookup"><span data-stu-id="3f85c-192">mtgOutofDate</span></span>  <br/> |<span data-ttu-id="3f85c-193">0x00080000</span><span class="sxs-lookup"><span data-stu-id="3f85c-193">0x00080000</span></span>  <br/> |
|<span data-ttu-id="3f85c-194">mtgDelegated</span><span class="sxs-lookup"><span data-stu-id="3f85c-194">mtgDelegated</span></span>  <br/> |<span data-ttu-id="3f85c-195">0x00100000</span><span class="sxs-lookup"><span data-stu-id="3f85c-195">0x00100000</span></span>  <br/> |
   
## <a name="replication-api"></a><span data-ttu-id="3f85c-196">复制 API</span><span class="sxs-lookup"><span data-stu-id="3f85c-196">About the Replication API</span></span>

<span data-ttu-id="3f85c-197">本部分包含常量定义、MAPI 接口声明，以及复制 API 的类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-197">This section contains constant definitions, MAPI interface declarations, and class and interface identifiers for the Replication API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="3f85c-198">常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-198">Constants</span></span>

<span data-ttu-id="3f85c-199">下面是识别 MAPI 服务提供商的 [MAPIUID](mapiuid.md) 结构：</span><span class="sxs-lookup"><span data-stu-id="3f85c-199">The following is a [MAPIUID](mapiuid.md) structure identifying a MAPI service provider:</span></span> 
  
```cpp
const MAPIUID g_muidProvPrvNST = 
 { 0xE9, 0x2F, 0xEB, 0x75, 0x96, 0x50, 0x44, 0x86, 
      0x83, 0xB8, 0x7D, 0xE5, 0x22, 0xAA, 0x49, 0x48 };
```

|||
|:-----|:-----|
|<span data-ttu-id="3f85c-200">DNH_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-200">DNH_OK</span></span>  <br/> |<span data-ttu-id="3f85c-201">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-201">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-202">DNT_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-202">DNT_OK</span></span>  <br/> |<span data-ttu-id="3f85c-203">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-203">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-204">HSF_LOCAL</span><span class="sxs-lookup"><span data-stu-id="3f85c-204">HSF_LOCAL</span></span>  <br/> |<span data-ttu-id="3f85c-205">0x00000008</span><span class="sxs-lookup"><span data-stu-id="3f85c-205">0x00000008</span></span>  <br/> |
|<span data-ttu-id="3f85c-206">HSF_COPYDESTRUCTIVE</span><span class="sxs-lookup"><span data-stu-id="3f85c-206">HSF_COPYDESTRUCTIVE</span></span>  <br/> |<span data-ttu-id="3f85c-207">0x00000010</span><span class="sxs-lookup"><span data-stu-id="3f85c-207">0x00000010</span></span>  <br/> |
|<span data-ttu-id="3f85c-208">HSF_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-208">HSF_OK</span></span>  <br/> |<span data-ttu-id="3f85c-209">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-209">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-210">MDB_OST_LOGON_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3f85c-210">MDB_OST_LOGON_UNICODE</span></span>  <br/> |<span data-ttu-id="3f85c-211">((ULONG) 0x00000800)</span><span class="sxs-lookup"><span data-stu-id="3f85c-211">((ULONG) 0x00000800)</span></span>  <br/> |
|<span data-ttu-id="3f85c-212">MDB_OST_LOGON_ANSI</span><span class="sxs-lookup"><span data-stu-id="3f85c-212">MDB_OST_LOGON_ANSI</span></span>  <br/> |<span data-ttu-id="3f85c-213">((ULONG) 0x00001000)</span><span class="sxs-lookup"><span data-stu-id="3f85c-213">((ULONG) 0x00001000)</span></span>  <br/> |
|<span data-ttu-id="3f85c-214">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="3f85c-214">SHOW_SOFT_DELETES</span></span>  <br/> |<span data-ttu-id="3f85c-215">((ULONG) 0x00000002)</span><span class="sxs-lookup"><span data-stu-id="3f85c-215">((ULONG) 0x00000002)</span></span>  <br/> |
|<span data-ttu-id="3f85c-216">SS_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="3f85c-216">SS_ACTIVE</span></span>  <br/> |<span data-ttu-id="3f85c-217">0</span><span class="sxs-lookup"><span data-stu-id="3f85c-217">{0}</span></span>  <br/> |
|<span data-ttu-id="3f85c-218">SS_SUSPENDED</span><span class="sxs-lookup"><span data-stu-id="3f85c-218">SS_SUSPENDED</span></span>  <br/> |<span data-ttu-id="3f85c-219">1</span><span class="sxs-lookup"><span data-stu-id="3f85c-219">-1</span></span>  <br/> |
|<span data-ttu-id="3f85c-220">SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="3f85c-220">SYNC_UPLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="3f85c-221">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-221">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-222">SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="3f85c-222">SYNC_DOWNLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="3f85c-223">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-223">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-224">SYNC_UPLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="3f85c-224">SYNC_UPLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="3f85c-225">0x00000040</span><span class="sxs-lookup"><span data-stu-id="3f85c-225">0x00000040</span></span>  <br/> |
|<span data-ttu-id="3f85c-226">SYNC_DOWNLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="3f85c-226">SYNC_DOWNLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="3f85c-227">0x00000080</span><span class="sxs-lookup"><span data-stu-id="3f85c-227">0x00000080</span></span>  <br/> |
|<span data-ttu-id="3f85c-228">SYNC_OUTGOING_MAIL</span><span class="sxs-lookup"><span data-stu-id="3f85c-228">SYNC_OUTGOING_MAIL</span></span>  <br/> |<span data-ttu-id="3f85c-229">0x00000200</span><span class="sxs-lookup"><span data-stu-id="3f85c-229">0x00000200</span></span>  <br/> |
|<span data-ttu-id="3f85c-230">SYNC_BACKGROUND</span><span class="sxs-lookup"><span data-stu-id="3f85c-230">SYNC_BACKGROUND</span></span>  <br/> |<span data-ttu-id="3f85c-231">0x00001000</span><span class="sxs-lookup"><span data-stu-id="3f85c-231">0x00001000</span></span>  <br/> |
|<span data-ttu-id="3f85c-232">SYNC_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="3f85c-232">SYNC_THESE_FOLDERS</span></span>  <br/> |<span data-ttu-id="3f85c-233">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-233">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-234">SYNC_HEADERS</span><span class="sxs-lookup"><span data-stu-id="3f85c-234">SYNC_HEADERS</span></span>  <br/> |<span data-ttu-id="3f85c-235">0x02000000</span><span class="sxs-lookup"><span data-stu-id="3f85c-235">0x02000000</span></span>  <br/> |
|<span data-ttu-id="3f85c-236">UPC_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-236">UPC_OK</span></span>  <br/> |<span data-ttu-id="3f85c-237">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-237">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-238">UPD_ASSOC</span><span class="sxs-lookup"><span data-stu-id="3f85c-238">UPD_ASSOC</span></span>  <br/> |<span data-ttu-id="3f85c-239">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-239">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-240">UPD_MOV</span><span class="sxs-lookup"><span data-stu-id="3f85c-240">UPD_MOV</span></span>  <br/> |<span data-ttu-id="3f85c-241">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-241">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-242">UPD_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-242">UPD_OK</span></span>  <br/> |<span data-ttu-id="3f85c-243">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-243">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-244">UPD_MOVED</span><span class="sxs-lookup"><span data-stu-id="3f85c-244">UPD_MOVED</span></span>  <br/> |<span data-ttu-id="3f85c-245">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-245">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-246">UPD_UPDATE</span><span class="sxs-lookup"><span data-stu-id="3f85c-246">UPD_UPDATE</span></span>  <br/> |<span data-ttu-id="3f85c-247">0x00040000</span><span class="sxs-lookup"><span data-stu-id="3f85c-247">0x00040000</span></span>  <br/> |
|<span data-ttu-id="3f85c-248">UPD_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3f85c-248">UPD_COMMIT</span></span>  <br/> |<span data-ttu-id="3f85c-249">0x00080000</span><span class="sxs-lookup"><span data-stu-id="3f85c-249">0x00080000</span></span>  <br/> |
|<span data-ttu-id="3f85c-250">UPF_NEW</span><span class="sxs-lookup"><span data-stu-id="3f85c-250">UPF_NEW</span></span>  <br/> |<span data-ttu-id="3f85c-251">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-251">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-252">UPF_MOD_PARENT</span><span class="sxs-lookup"><span data-stu-id="3f85c-252">UPF_MOD_PARENT</span></span>  <br/> |<span data-ttu-id="3f85c-253">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-253">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-254">UPF_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="3f85c-254">UPF_MOD_PROPS</span></span>  <br/> |<span data-ttu-id="3f85c-255">0x00000004</span><span class="sxs-lookup"><span data-stu-id="3f85c-255">0x00000004</span></span>  <br/> |
|<span data-ttu-id="3f85c-256">UPF_DEL</span><span class="sxs-lookup"><span data-stu-id="3f85c-256">UPF_DEL</span></span>  <br/> |<span data-ttu-id="3f85c-257">0x00000008</span><span class="sxs-lookup"><span data-stu-id="3f85c-257">0x00000008</span></span>  <br/> |
|<span data-ttu-id="3f85c-258">UPF_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-258">UPF_OK</span></span>  <br/> |<span data-ttu-id="3f85c-259">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-259">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-260">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-260">UPH_OK</span></span>  <br/> |<span data-ttu-id="3f85c-261">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-261">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-262">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="3f85c-262">UPM_ASSOC</span></span>  <br/> |<span data-ttu-id="3f85c-263">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-263">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-264">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="3f85c-264">UPM_NEW</span></span>  <br/> |<span data-ttu-id="3f85c-265">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-265">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-266">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="3f85c-266">UPM_MOV</span></span>  <br/> |<span data-ttu-id="3f85c-267">0x00000004</span><span class="sxs-lookup"><span data-stu-id="3f85c-267">0x00000004</span></span>  <br/> |
|<span data-ttu-id="3f85c-268">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="3f85c-268">UPM_MOD_PROPS</span></span>  <br/> |<span data-ttu-id="3f85c-269">0x00000008</span><span class="sxs-lookup"><span data-stu-id="3f85c-269">0x00000008</span></span>  <br/> |
|<span data-ttu-id="3f85c-270">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="3f85c-270">UPM_HEADER</span></span>  <br/> |<span data-ttu-id="3f85c-271">0x00000010</span><span class="sxs-lookup"><span data-stu-id="3f85c-271">0x00000010</span></span>  <br/> |
|<span data-ttu-id="3f85c-272">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-272">UPM_OK</span></span>  <br/> |<span data-ttu-id="3f85c-273">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-273">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-274">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="3f85c-274">UPM_MOVED</span></span>  <br/> |<span data-ttu-id="3f85c-275">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-275">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-276">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3f85c-276">UPM_COMMIT</span></span>  <br/> |<span data-ttu-id="3f85c-277">0x00040000</span><span class="sxs-lookup"><span data-stu-id="3f85c-277">0x00040000</span></span>  <br/> |
|<span data-ttu-id="3f85c-278">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="3f85c-278">UPM_DELETE</span></span>  <br/> |<span data-ttu-id="3f85c-279">0x00080000</span><span class="sxs-lookup"><span data-stu-id="3f85c-279">0x00080000</span></span>  <br/> |
|<span data-ttu-id="3f85c-280">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="3f85c-280">UPM_SAVE</span></span>  <br/> |<span data-ttu-id="3f85c-281">0x00100000</span><span class="sxs-lookup"><span data-stu-id="3f85c-281">0x00100000</span></span>  <br/> |
|<span data-ttu-id="3f85c-282">UPR_ASSOC</span><span class="sxs-lookup"><span data-stu-id="3f85c-282">UPR_ASSOC</span></span>  <br/> |<span data-ttu-id="3f85c-283">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-283">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-284">UPR_READ</span><span class="sxs-lookup"><span data-stu-id="3f85c-284">UPR_READ</span></span>  <br/> |<span data-ttu-id="3f85c-285">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-285">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-286">UPR_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-286">UPR_OK</span></span>  <br/> |<span data-ttu-id="3f85c-287">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-287">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-288">UPR_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3f85c-288">UPR_COMMIT</span></span>  <br/> |<span data-ttu-id="3f85c-289">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-289">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-290">UPS_UPLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="3f85c-290">UPS_UPLOAD_ONLY</span></span>  <br/> |<span data-ttu-id="3f85c-291">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-291">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-292">UPS_DNLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="3f85c-292">UPS_DNLOAD_ONLY</span></span>  <br/> |<span data-ttu-id="3f85c-293">0x00000002</span><span class="sxs-lookup"><span data-stu-id="3f85c-293">0x00000002</span></span>  <br/> |
|<span data-ttu-id="3f85c-294">UPS_ONE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="3f85c-294">UPS_ONE_FOLDER</span></span>  <br/> |<span data-ttu-id="3f85c-295">0x00000004</span><span class="sxs-lookup"><span data-stu-id="3f85c-295">0x00000004</span></span>  <br/> |
|<span data-ttu-id="3f85c-296">UPS_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="3f85c-296">UPS_THESE_FOLDERS</span></span>  <br/> |<span data-ttu-id="3f85c-297">0x00000080</span><span class="sxs-lookup"><span data-stu-id="3f85c-297">0x00000080</span></span>  <br/> |
|<span data-ttu-id="3f85c-298">UPS_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-298">UPS_OK</span></span>  <br/> |<span data-ttu-id="3f85c-299">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-299">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-300">UPT_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-300">UPT_OK</span></span>  <br/> |<span data-ttu-id="3f85c-301">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-301">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-302">UPT_PUBLIC</span><span class="sxs-lookup"><span data-stu-id="3f85c-302">UPT_PUBLIC</span></span>  <br/> |<span data-ttu-id="3f85c-303">0x00000001</span><span class="sxs-lookup"><span data-stu-id="3f85c-303">0x00000001</span></span>  <br/> |
|<span data-ttu-id="3f85c-304">UPV_ERROR</span><span class="sxs-lookup"><span data-stu-id="3f85c-304">UPV_ERROR</span></span>  <br/> |<span data-ttu-id="3f85c-305">0x00010000</span><span class="sxs-lookup"><span data-stu-id="3f85c-305">0x00010000</span></span>  <br/> |
|<span data-ttu-id="3f85c-306">UPV_DIRTY</span><span class="sxs-lookup"><span data-stu-id="3f85c-306">UPV_DIRTY</span></span>  <br/> |<span data-ttu-id="3f85c-307">0x00020000</span><span class="sxs-lookup"><span data-stu-id="3f85c-307">0x00020000</span></span>  <br/> |
|<span data-ttu-id="3f85c-308">UPV_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3f85c-308">UPV_COMMIT</span></span>  <br/> |<span data-ttu-id="3f85c-309">0x00040000</span><span class="sxs-lookup"><span data-stu-id="3f85c-309">0x00040000</span></span>  <br/> |
   
### <a name="interface-declarations"></a><span data-ttu-id="3f85c-310">接口声明</span><span class="sxs-lookup"><span data-stu-id="3f85c-310">Interface declarations</span></span>

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportHierarchyChanges,PXIHC);
```

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportContentsChanges,PXICC);
```

### <a name="interface-identifiers"></a><span data-ttu-id="3f85c-311">接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-311">Interface identifiers</span></span>

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

<span data-ttu-id="3f85c-312">将以下两个接口标识符与 [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、[IMAPISession::OpenEntry](imapisession-openentry.md) 或 [IMsgStore::OpenEntry](imsgstore-openentry.md) 配合使用以分别打开并忽略针对文件夹对象和邮件对象的任何提供商检查。</span><span class="sxs-lookup"><span data-stu-id="3f85c-312">Use the two following interface identifiers with [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), or [IMsgStore::OpenEntry](imsgstore-openentry.md) to open and ignore any provider check on a folder object and a message object, respectively.</span></span> 
  
```cpp
//{57D333A0-F589-4b23-A3F9-85F82FEC153C}
DEFINE_GUID (IID_IMAPIFolderNoProvChk, 0x57D333A0, 0xF589, 0x4b23, 0xA3, 0xF9, 0x85, 0xF8, 0x2F, 0xEC, 0x15, 0x3C)
```

```cpp
//{C3505457-7B2E-4c3b-A8D6-6DD949BB97A1}
DEFINE_GUID (IID_IMessageNoProvChk, 0xC3505457, 0x7B2E, 0x4c3b, 0xA8, 0xD6, 0x6D, 0xD9, 0x49, 0xBB, 0x97, 0xA1)
```

## <a name="mapi-store"></a><span data-ttu-id="3f85c-313">MAPI 存储</span><span class="sxs-lookup"><span data-stu-id="3f85c-313">MAPI store</span></span>

<span data-ttu-id="3f85c-314">本部分包含常量定义和 API 使用的与 MAPI 存储接合的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-314">This section contains constant definitions and interface identifiers used by APIs that interface with a MAPI store.</span></span>
  
### <a name="constants"></a><span data-ttu-id="3f85c-315">常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-315">Constants</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="3f85c-316">fnevIndexing</span><span class="sxs-lookup"><span data-stu-id="3f85c-316">fnevIndexing</span></span>  <br/> |<span data-ttu-id="3f85c-317">((ULONG) 0x00010000)</span><span class="sxs-lookup"><span data-stu-id="3f85c-317">((ULONG) 0x00010000)</span></span>  <br/> |<span data-ttu-id="3f85c-318">存储提供程序可以指定**[通知](notification.md)** 结构 **ulEventType** 成员中的 **fnevIndexing**，以通知索引器对象已准备好进行索引。</span><span class="sxs-lookup"><span data-stu-id="3f85c-318">A store provider can specify **fnevIndexing** in the **ulEventType** member of the **[NOTIFICATION](notification.md)** structure to notify the indexer that an object is ready for indexing.</span></span> <span data-ttu-id="3f85c-319">**通知**结构的 **info** 成员包含 **[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="3f85c-319">The **info** member of the **NOTIFICATION** structure contains an **[EXTENDED_NOTIFICATION](extended_notification.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="3f85c-320">FS_NONE</span><span class="sxs-lookup"><span data-stu-id="3f85c-320">FS_NONE</span></span>  <br/> |<span data-ttu-id="3f85c-321">0x00</span><span class="sxs-lookup"><span data-stu-id="3f85c-321">0x00</span></span>  <br/> |<span data-ttu-id="3f85c-322">客户端可以调用 **[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** 并检查返回的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3f85c-322">A client can call **[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** and check for the returned bitmask.</span></span> <span data-ttu-id="3f85c-323">**FS_NONE** 指示文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="3f85c-323">**FS_NONE** indicates that the folder does not support sharing.</span></span>  <br/> |
|<span data-ttu-id="3f85c-324">FS_SUPPORTS_SHARING</span><span class="sxs-lookup"><span data-stu-id="3f85c-324">FS_SUPPORTS_SHARING</span></span>  <br/> |<span data-ttu-id="3f85c-325">0x01</span><span class="sxs-lookup"><span data-stu-id="3f85c-325">0x01</span></span>  <br/> |<span data-ttu-id="3f85c-326">客户端可以调用 **IFolderSupport::GetSupportMask** 并检查返回的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3f85c-326">A client can call **IFolderSupport::GetSupportMask** and check for the returned bitmask.</span></span> <span data-ttu-id="3f85c-327">**FS_SUPPORTS_SHARING** 指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="3f85c-327">**FS_SUPPORTS_SHARING** indicates that the folder supports sharing.</span></span>  <br/> |
|<span data-ttu-id="3f85c-328">INDEXING_SEARCH_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f85c-328">INDEXING_SEARCH_OWNER</span></span>  <br/> |<span data-ttu-id="3f85c-329">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="3f85c-329">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="3f85c-330">标识将通知推送到索引器指示对象已准备好索引的进程。</span><span class="sxs-lookup"><span data-stu-id="3f85c-330">Identifies the process that is pushing a notification to an indexer that an object is ready for indexing.</span></span>  <br/> |
|<span data-ttu-id="3f85c-331">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="3f85c-331">MNID_ID</span></span>  <br/> |<span data-ttu-id="3f85c-332">如 Microsoft Windows 软件开发工具包 (SDK) 头文件 mapidefs.h 中所定义的</span><span class="sxs-lookup"><span data-stu-id="3f85c-332">As defined in the Microsoft Windows Software Development Kit (SDK) header file mapidefs.h</span></span>  <br/> |<span data-ttu-id="3f85c-333">**[MAPINAMEID](mapinameid.md)** 结构的 **ulKind** 字段的值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-333">A value for the **ulKind** field of the **[MAPINAMEID](mapinameid.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="3f85c-334">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="3f85c-334">MNID_STRING</span></span>  <br/> |<span data-ttu-id="3f85c-335">如 Microsoft Windows 软件开发工具包 (SDK) 头文件 mapidefs.h 中所定义。</span><span class="sxs-lookup"><span data-stu-id="3f85c-335">As defined in the Microsoft Windows Software Development Kit (SDK) header file mapidefs.h.</span></span>  <br/> |<span data-ttu-id="3f85c-336">**[MAPINAMEID](mapinameid.md)** 结构的 **ulKind** 字段的值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-336">A value for the **ulKind** field of the **[MAPINAMEID](mapinameid.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="3f85c-337">MSCAP_RES_ANNOTATION</span><span class="sxs-lookup"><span data-stu-id="3f85c-337">MSCAP_RES_ANNOTATION</span></span>  <br/> |<span data-ttu-id="3f85c-338">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="3f85c-338">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="3f85c-339">如果客户端为 **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)** 指定 *mscapSelector* 中的 **MSCAP_SEL_RESTRICTION**，如果存储忽略限制中的无效参数，则 **GetCapabilities** 可能会返回该值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-339">If a client specifies **MSCAP_SEL_RESTRICTION** in  *mscapSelector*  for **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)**, **GetCapabilities** can return this value if the store ignores invalid parameters in a restriction.</span></span>  <br/> |
|<span data-ttu-id="3f85c-340">MSCAP_SECURE_FOLDER_HOMEPAGES</span><span class="sxs-lookup"><span data-stu-id="3f85c-340">MSCAP_SECURE_FOLDER_HOMEPAGES</span></span>  <br/> |<span data-ttu-id="3f85c-341">((ULONG) 0x00000020)</span><span class="sxs-lookup"><span data-stu-id="3f85c-341">((ULONG) 0x00000020)</span></span>  <br/> |<span data-ttu-id="3f85c-342">如果客户端为 **IMSCapabilities::GetCapabilities** 指定 *mscapSelector* 中的 **MSCAP_SEL_FOLDER**，如果存储是支持文件夹主页的非默认存储，则 **GetCapabilities** 可能会返回该值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-342">If a client specifies **MSCAP_SEL_FOLDER** in  *mscapSelector*  for **IMSCapabilities::GetCapabilities**, **GetCapabilities** can return this value if the store is a non-default store that supports folder home pages.</span></span>  <br/> |
|<span data-ttu-id="3f85c-343">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-343">STORE_PUSHER_OK</span></span>  <br/> |<span data-ttu-id="3f85c-344">((ULONG) 0x00800000)</span><span class="sxs-lookup"><span data-stu-id="3f85c-344">((ULONG) 0x00800000)</span></span>  <br/> |<span data-ttu-id="3f85c-345">客户端可以获取属性 **[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 来确定邮件存储的特征。</span><span class="sxs-lookup"><span data-stu-id="3f85c-345">A client can get the property **[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** to determine the characteristic of a message store.</span></span> <span data-ttu-id="3f85c-346">如果存储提供程序在位掩码中设置 **STORE_PUSHER_OK** 标记，这意味着 MAPI 协议处理程序不会对存储区进行爬网，且存储区负责通过通知将任何更改推送到索引器来索引邮件。</span><span class="sxs-lookup"><span data-stu-id="3f85c-346">If the store provider sets the **STORE_PUSHER_OK** flag in the bitmask, that means the MAPI Protocol Handler will not crawl the store, and the store is responsible to push any changes through notifications to the indexer to have messages indexed.</span></span>  <br/> |
   
### <a name="definitions-for-namespaces"></a><span data-ttu-id="3f85c-347">命名空间定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-347">Definitions for namespaces</span></span>

<span data-ttu-id="3f85c-348">以下全局唯一标识符 (GUID) 代表命名属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3f85c-348">The following globally unique identifiers (GUIDs) represent the namespaces of named properties.</span></span> <span data-ttu-id="3f85c-349">他们已通过 MAPI 协议处理程序 (PH) 编制索引，并被记录为只读。</span><span class="sxs-lookup"><span data-stu-id="3f85c-349">They are indexed by the MAPI Protocol Handler (PH), and are documented as read-only.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3f85c-350">命名属性不应用于创建或修改项。</span><span class="sxs-lookup"><span data-stu-id="3f85c-350">The named properties should not be used to create or modify items.</span></span> 
  
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

#### <a name="mnidid-properties"></a><span data-ttu-id="3f85c-351">MNID_ID Properties</span><span class="sxs-lookup"><span data-stu-id="3f85c-351">MNID_ID Properties</span></span>
  
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

#### <a name="mnidstring-properties"></a><span data-ttu-id="3f85c-352">MNID_STRING Properties</span><span class="sxs-lookup"><span data-stu-id="3f85c-352">MNID_STRING Properties</span></span>
  
```cpp
// In PS_PUBLIC_STRINGS 
"Keywords"
```

```cpp
// In PS_INTERNET_HEADERS
"return-path"
```

### <a name="interface-identifiers"></a><span data-ttu-id="3f85c-353">接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-353">Interface identifiers</span></span>

```cpp
//{00375ac3-ecaf-4ef8-a527-34f452fa9c67}
DEFINE_GUID(IID_IFolderSupport, 0x00375ac3, 0xecaf, 0x4ef8, 0xa5, 0x27, 0x34, 0xf4, 0x52, 0xfa, 0x9c, 0x67);

```

```cpp
//{29F3AB10-554d-11d0-a97c-00a0c911f50a}
#define DEFINE_PRXGUID(_name, _l) DEFINE_GUID(_name, (0x29f3ab10 + _l), 0x554d, 0x11d0, 0xa9, 0x7c, 0x00, 0xa0, 0xc9, 0x11, 0xf5, 0x0a) 
DEFINE_PRXGUID(IID_IProxyStoreObject, 0x00000000L);
```

<span data-ttu-id="3f85c-354">使用在 Windows SDK 头文件 guiddef.h 中定义的 `DEFINE_OLEGUID` 宏将以下 GUID 符号名称与及其值相关联。</span><span class="sxs-lookup"><span data-stu-id="3f85c-354">Use the  `DEFINE_OLEGUID` macro defined in the Windows SDK header file guiddef.h to associate the following GUID symbolic name with its value.</span></span> 
  
```cpp
//{00020393-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_IMSCapabilities, 0x00020393, 0, 0)

```

## <a name="mapi-address-book-constants"></a><span data-ttu-id="3f85c-355">MAPI 通讯簿常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-355">MAPI Address Book constants</span></span>

<span data-ttu-id="3f85c-356">本部分包含 MAPI 通讯簿的常量定义。</span><span class="sxs-lookup"><span data-stu-id="3f85c-356">This section contains constant definitions for the MAPI Address Book.</span></span>
  
### <a name="constants"></a><span data-ttu-id="3f85c-357">常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-357">Constants</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="3f85c-358">CONTAB_ROOT</span><span class="sxs-lookup"><span data-stu-id="3f85c-358">CONTAB_ROOT</span></span>  <br/> |<span data-ttu-id="3f85c-359">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="3f85c-359">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="3f85c-360">MAPI 通讯簿对象的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f85c-360">The root folder for a MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="3f85c-361">CONTAB_SUBROOT</span><span class="sxs-lookup"><span data-stu-id="3f85c-361">CONTAB_SUBROOT</span></span>  <br/> |<span data-ttu-id="3f85c-362">((ULONG) 0x00000002)</span><span class="sxs-lookup"><span data-stu-id="3f85c-362">((ULONG) 0x00000002)</span></span>  <br/> |<span data-ttu-id="3f85c-363">MAPI 通讯簿对象的根文件夹内包含一个子文件。</span><span class="sxs-lookup"><span data-stu-id="3f85c-363">A subfolder contained within the root folder of the MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="3f85c-364">CONTAB_CONTAINER</span><span class="sxs-lookup"><span data-stu-id="3f85c-364">CONTAB_CONTAINER</span></span>  <br/> |<span data-ttu-id="3f85c-365">((ULONG) 0x00000003)</span><span class="sxs-lookup"><span data-stu-id="3f85c-365">((ULONG) 0x00000003)</span></span>  <br/> |<span data-ttu-id="3f85c-366">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="3f85c-366">An address book container object.</span></span>  <br/> |
|<span data-ttu-id="3f85c-367">CONTAB_USER</span><span class="sxs-lookup"><span data-stu-id="3f85c-367">CONTAB_USER</span></span>  <br/> |<span data-ttu-id="3f85c-368">((ULONG) 0x00000004)</span><span class="sxs-lookup"><span data-stu-id="3f85c-368">((ULONG) 0x00000004)</span></span>  <br/> |<span data-ttu-id="3f85c-369">消息传递用户对象。</span><span class="sxs-lookup"><span data-stu-id="3f85c-369">A messaging user object.</span></span>  <br/> |
|<span data-ttu-id="3f85c-370">CONTAB_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="3f85c-370">CONTAB_DISTLIST</span></span>  <br/> |<span data-ttu-id="3f85c-371">((ULONG) 0x00000005)</span><span class="sxs-lookup"><span data-stu-id="3f85c-371">((ULONG) 0x00000005)</span></span>  <br/> |<span data-ttu-id="3f85c-372">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="3f85c-372">A distribution list object.</span></span>  <br/> |
   
## <a name="additional-mapi-constants"></a><span data-ttu-id="3f85c-373">其他 MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3f85c-373">Additional MAPI constants</span></span>

<span data-ttu-id="3f85c-374">本部分包含包括错误代码在内的常量定义，和以前未公开和记录的 MAPI API 使用的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f85c-374">This section contains constant definitions including error codes, and interface identifiers used by MAPI APIs that were not previously exposed and documented.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3f85c-375">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="3f85c-375">DIALOG_MODAL</span></span>  <br/> |<span data-ttu-id="3f85c-376">((ULONG) 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="3f85c-376">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="3f85c-377">当客户端调用 [IAddrBook::Details](iaddrbook-details.md) 方法时，客户端必须在 _ulFlags_ 参数中设置 **DIALOG_MODAL** 标记，以显示模式对话框框，其中显示了有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3f85c-377">When a client calls the [IAddrBook::Details](iaddrbook-details.md) method, the client must set the **DIALOG_MODAL** flag in the  _ulFlags_ parameter to display the modal dialog box showing the details about a particular address book entry.</span></span> <span data-ttu-id="3f85c-378">此常量在 mapidefs.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="3f85c-378">This constant is defined in mapidefs.h.</span></span>  <br/> |
|<span data-ttu-id="3f85c-379">ITEMPROC_FORCE</span><span class="sxs-lookup"><span data-stu-id="3f85c-379">ITEMPROC_FORCE</span></span>  <br/> |<span data-ttu-id="3f85c-380">0x00000800</span><span class="sxs-lookup"><span data-stu-id="3f85c-380">0x00000800</span></span>  <br/> |<span data-ttu-id="3f85c-381">在 Outlook 2007 中，包装的 PST 存储区会在通知 MAPI 客户端新邮件之前，对新邮件执行规则和垃圾邮件筛选处理。</span><span class="sxs-lookup"><span data-stu-id="3f85c-381">In Outlook 2007, wrapped PST stores have rules and spam filtering processed on new messages before MAPI clients are notified of the new messages.</span></span> <span data-ttu-id="3f85c-382">使用 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 方法在 PST 存储区中创建新邮件的提供商或客户端应在 [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法的 _ulFlags_ 参数中设置 **ITEMPROC_FORCE** 标记，以便向 PST 存储区表明，在存储区通知任何侦听客户端有关新邮件到达之前，该邮件有资格进行规则处理。</span><span class="sxs-lookup"><span data-stu-id="3f85c-382">A provider or client using the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create a new message in PST stores should set the **ITEMPROC_FORCE** flag in the  _ulFlags_ parameter of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to indicate to the PST store that the message is eligible for rules processing before the store notifies any listening client of the arrival of the new message.</span></span> <span data-ttu-id="3f85c-383">请注意，此类规则处理仅适用于在除 Microsoft Exchange Server 以外的服务器上创建的新邮件，因为 Exchange Server 处理服务器上的邮件规则。</span><span class="sxs-lookup"><span data-stu-id="3f85c-383">Note that such rules processing only applies to new messages created on a server that is not a Microsoft Exchange Server, because Exchange Server processes rules for messages on the server.</span></span> <span data-ttu-id="3f85c-384">因此创建邮件的提供商或客户端必须将此标记与 **NON_EMS_XP_SAVE** 一起传递，表示服务器不是 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="3f85c-384">Hence the provider or client creating the message must pass this flag in combination with **NON_EMS_XP_SAVE**, which indicates the server is not an Exchange server.</span></span>  <br/> |
| <span data-ttu-id="3f85c-385">MAPI_BG_SESSION</span><span class="sxs-lookup"><span data-stu-id="3f85c-385">MAPI_BG_SESSION</span></span>  <br/> |<span data-ttu-id="3f85c-386">0x00200000</span><span class="sxs-lookup"><span data-stu-id="3f85c-386">0x00200000</span></span>  <br/> |<span data-ttu-id="3f85c-387">客户端可以调用 [MAPILogonEx](mapilogonex.md) 函数，设置 _flFlags_ 参数中的 **MAPI_BG_SESSION** 标记，以登录到会话并在后台执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3f85c-387">A client can call the [MAPILogonEx](mapilogonex.md) function, setting the **MAPI_BG_SESSION** flag in the  _flFlags_ parameter to log on to a session and carry out any operations in the background.</span></span> <span data-ttu-id="3f85c-388">一般情况下，如果客户端打算在后台线程，或者在独立过程中以在前台线程上不显眼的方式执行处理，它应调用带 **MAPI_BG_SESSION** 标记的 [MAPILogonEx](mapilogonex.md)。</span><span class="sxs-lookup"><span data-stu-id="3f85c-388">In general, if a client intends to do processing on a background thread or in a separate process in a manner that is unobtrusive to the foreground thread, it should call [MAPILogonEx](mapilogonex.md) with the **MAPI_BG_SESSION** flag.</span></span> <span data-ttu-id="3f85c-389">使用此方法的一个示例是客户端应用程序，例如索引引擎，它会打开用于后台类型访问的个人文件夹文件 (PST)。</span><span class="sxs-lookup"><span data-stu-id="3f85c-389">An example where this is used is a client application, such as an indexing engine, opening a Personal Folders File (PST) for background type access.</span></span>  <br/> |
|<span data-ttu-id="3f85c-390">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="3f85c-390">MAPI_CACHE_ONLY</span></span>  <br/> |<span data-ttu-id="3f85c-391">0x00004000</span><span class="sxs-lookup"><span data-stu-id="3f85c-391">0x00004000</span></span>  <br/> |<span data-ttu-id="3f85c-392">客户端可以调用 [IAddrBook::OpenEntry](iaddrbook-openentry.md) 方法时，设置 _ulFlags_ 参数中的 **MAPI_CACHE_ONLY** 标记来打开通讯簿条目，随后仅从缓存中访问它。</span><span class="sxs-lookup"><span data-stu-id="3f85c-392">A client can call the [IAddrBook::OpenEntry](iaddrbook-openentry.md) method, setting the **MAPI_CACHE_ONLY** flag in the  _ulFlags_ parameter to open an address book entry and to access it subsequently only from the cache.</span></span> <span data-ttu-id="3f85c-393">使用此方法的一个示例是想要在缓存 Exchange 模式中打开全局地址列表，并从缓存访问该通讯簿条目的客户端应用程序，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="3f85c-393">An example where this is used is a client application that wants to open the Global Address List in Cached Exchange mode and access an entry in that Address Book from the cache without creating traffic between the client and the server.</span></span>  <br/> |
|<span data-ttu-id="3f85c-394">MAPI_DIALOG_MODELESS</span><span class="sxs-lookup"><span data-stu-id="3f85c-394">MAPI_DIALOG_MODELESS</span></span>  <br/> |<span data-ttu-id="3f85c-395">0x0000000C</span><span class="sxs-lookup"><span data-stu-id="3f85c-395">0x0000000C</span></span>  <br/> |<span data-ttu-id="3f85c-396">此值可以传递给 _ulFlags_ 参数中的简单 MAPI MAPISendMail 函数，以指定由默认邮件应用程序显示无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="3f85c-396">This value can be passed to the Simple MAPI MAPISendMail function in the  _ulFlags_ parameter to specify that a modeless dialog box is displayed by the default mail application.</span></span> <span data-ttu-id="3f85c-397">如果此标记和 MAPI_DIALOG (0x00000008) 均未设置，将不会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="3f85c-397">If neither this flag nor MAPI_DIALOG (0x00000008) is set, no dialog box is displayed.</span></span>  <br/> |
|<span data-ttu-id="3f85c-398">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="3f85c-398">MAPI_NO_CACHE</span></span>  <br/> |<span data-ttu-id="3f85c-399">0x00000200</span><span class="sxs-lookup"><span data-stu-id="3f85c-399">0x00000200</span></span>  <br/> |<span data-ttu-id="3f85c-400">如果 Microsoft Office Outlook 处于缓存 Exchange 模式且在缓存模式中打开了一个存储区，客户端或服务提供商可以调用 [IMsgStore::OpenEntry](imsgstore-openentry.md)，设置 _ulFlags_ 参数的 **MAPI_NO_CACHE** 标记，以便在远程存储区上打开某个项目或文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f85c-400">If Microsoft Office Outlook is in Cached Exchange Mode and a store has been opened in cached mode, a client or service provider can call [IMsgStore::OpenEntry](imsgstore-openentry.md), setting the **MAPI_NO_CACHE** flag in the  _ulFlags_ parameter to open an item or a folder on the remote store.</span></span> <span data-ttu-id="3f85c-401">请注意，如果在远程服务器上使用 **MDB_ONLINE** 标记打开邮件存储区，则无需使用 **MAPI_NO_CACHE** 标记。</span><span class="sxs-lookup"><span data-stu-id="3f85c-401">Note that if you open the message store with the **MDB_ONLINE** flag on the remote server, you do not have to use the **MAPI_NO_CACHE** flag.</span></span>  <br/> |
|<span data-ttu-id="3f85c-402">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3f85c-402">MAPI_UNICODE</span></span>  <br/> |<span data-ttu-id="3f85c-403">0x80000000</span><span class="sxs-lookup"><span data-stu-id="3f85c-403">0x80000000</span></span>  <br/> |<span data-ttu-id="3f85c-404">客户端或服务提供商可以调用 [OpenIMsgOnIStg](openimsgonistg.md) 函数，设置 _ulFlags_ 参数中的 **MAPI_UNICODE** 标记，来创建 Unicode.msg 文件。</span><span class="sxs-lookup"><span data-stu-id="3f85c-404">A client or service provider can call the [OpenIMsgOnIStg](openimsgonistg.md) function, setting the **MAPI_UNICODE** flag in the  _ulFlags_ parameter to create Unicode .msg files.</span></span> <span data-ttu-id="3f85c-405">生成的 [IMessage: IMAPIProp](imessageimapiprop.md) 文件显示 **STORE_UNICODE_OK** 位于其 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中，且支持 Unicode 属性。</span><span class="sxs-lookup"><span data-stu-id="3f85c-405">The resulting [IMessage : IMAPIProp](imessageimapiprop.md) file shows **STORE_UNICODE_OK** in its [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md) and supports Unicode properties.</span></span> <span data-ttu-id="3f85c-406">此常量在 mapidefs.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="3f85c-406">This constant is defined in mapidefs.h.</span></span>  <br/> |
|<span data-ttu-id="3f85c-407">MDB_ONLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-407">MDB_ONLINE</span></span>  <br/> |<span data-ttu-id="3f85c-408">0x00000100</span><span class="sxs-lookup"><span data-stu-id="3f85c-408">0x00000100</span></span>  <br/> |<span data-ttu-id="3f85c-409">如果 Outlook 处于缓存 Exchange 模式，客户端或服务提供商可以调用 [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) 方法，设置 _ulFlags_ 参数中的 **MDB_ONLINE** 标记，以覆盖与本地邮件存储区的连接，并打开远程服务器上的存储区。</span><span class="sxs-lookup"><span data-stu-id="3f85c-409">If Outlook is in Cached Exchange Mode, a client or service provider can call the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method, setting the **MDB_ONLINE** flag in the  _ulFlags_ parameter to override the connection to the local message store and open the store on the remote server.</span></span> <span data-ttu-id="3f85c-410">请注意，不能在同一个 MAPI 会话中同时在缓存模式和非缓存模式下打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="3f85c-410">Note that you cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="3f85c-411">如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="3f85c-411">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>  <br/> |
|<span data-ttu-id="3f85c-412">NON_EMS_XP_SAVE</span><span class="sxs-lookup"><span data-stu-id="3f85c-412">NON_EMS_XP_SAVE</span></span>  <br/> |<span data-ttu-id="3f85c-413">0x00001000</span><span class="sxs-lookup"><span data-stu-id="3f85c-413">0x00001000</span></span>  <br/> |<span data-ttu-id="3f85c-414">客户端可以调用 [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法，设置 _ulFlags_ 参数中的 **NON_EMS_XP_SAVE** 标记，以指示未从 Exchange 服务器传送邮件。</span><span class="sxs-lookup"><span data-stu-id="3f85c-414">A client can call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method, setting the **NON_EMS_XP_SAVE** flag in the  _ulFlags_ parameter to indicate that the message has not been delivered from an Exchange server.</span></span> <span data-ttu-id="3f85c-415">应将此标记与 _ulFlags_ 参数中的 **ITEMPROC_FORCE** 标记结合使用，向 PST 存储区表明，在 PST 存储区通知任何侦听客户端有关邮件到达之前，邮件有资格进行规则处理。</span><span class="sxs-lookup"><span data-stu-id="3f85c-415">This flag should be used in combination with the **ITEMPROC_FORCE** flag in the  _ulFlags_ parameter to indicate to a PST store that the message is eligible for rules processing before the PST store notifies any listening client of the arrival of the message.</span></span> <span data-ttu-id="3f85c-416">此规则仅适用于在除 Exchange 服务器以外的服务器上使用 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 创建的新邮件（这种情况下 Exchange 服务器已处理邮件上的规则）。</span><span class="sxs-lookup"><span data-stu-id="3f85c-416">This rules processing only applies to new messages that are created with [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) on a server that is not an Exchange server (in which case the Exchange server would have already processed rules on the message).</span></span>  <br/> |
|<span data-ttu-id="3f85c-417">SPAMFILTER_ONSAVE</span><span class="sxs-lookup"><span data-stu-id="3f85c-417">SPAMFILTER_ONSAVE</span></span>  <br/> |<span data-ttu-id="3f85c-418">0x00000080</span><span class="sxs-lookup"><span data-stu-id="3f85c-418">0x00000080</span></span>  <br/> |<span data-ttu-id="3f85c-419">客户端可以调用 [IMAPIProp::SaveChanges](imapiprop-savechanges.md)，设置 _ulFlags_ 参数中的 **SPAMFILTER_ONSAVE** 标记，以便在正在保存的邮件上启用垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="3f85c-419">A client can call [IMAPIProp::SaveChanges](imapiprop-savechanges.md), setting the **SPAMFILTER_ONSAVE** flag in the  _ulFlags_ parameter to enable spam filtering on a message that is being saved.</span></span> <span data-ttu-id="3f85c-420">垃圾邮件筛选支持只有在发件人的电子邮件地址类型为简单邮件传输协议 (SMTP) 且正在将邮件保存到个人文件夹文件 (PST) 存储区的情况下可用。</span><span class="sxs-lookup"><span data-stu-id="3f85c-420">Spam filtering support is available only if the sender's email address type is Simple Mail Transfer Protocol (SMTP), and the message is being saved to a store for a Personal Folders file (PST).</span></span>  <br/> |
|<span data-ttu-id="3f85c-421">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="3f85c-421">STORE_ITEMPROC</span></span>  <br/> |<span data-ttu-id="3f85c-422">0x00200000</span><span class="sxs-lookup"><span data-stu-id="3f85c-422">0x00200000</span></span>  <br/> |<span data-ttu-id="3f85c-423">如果在包装的 PST 存储区的 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中设置此标记，它表示在新邮件到达存储区时，存储区会单独在邮件上处理规则和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="3f85c-423">If this flag is set in the [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md) of a wrapped PST store, it indicates that when a new message arrives at the store, the store has rules and spam filtering processed on the message separately.</span></span> <span data-ttu-id="3f85c-424">存储区然后调用 [IMAPISupport::Notify](imapisupport-notify.md)，在[通知](notification.md)结构中设置作为参数传递的 **fnevNewMail**，并将新邮件的详细信息传递到侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="3f85c-424">The store then calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and passing the details of the new message to a listening client.</span></span> <span data-ttu-id="3f85c-425">随后，当侦听客户端收到通知，它不会处理邮件上的规则。</span><span class="sxs-lookup"><span data-stu-id="3f85c-425">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span>  <br/> |
|<span data-ttu-id="3f85c-426">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="3f85c-426">STORE_UNICODE_OK</span></span>  <br/> |<span data-ttu-id="3f85c-427">0x00040000</span><span class="sxs-lookup"><span data-stu-id="3f85c-427">0x00040000</span></span>  <br/> |<span data-ttu-id="3f85c-428">如果此标志包含在 [PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中，它表示存储支持 Unicode 存储。</span><span class="sxs-lookup"><span data-stu-id="3f85c-428">If this flag is included in the [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md), it indicates that the store supports Unicode storage.</span></span> <span data-ttu-id="3f85c-429">客户端可以查找标记以决定是否请求或将 Unicode 信息保存到存储区。</span><span class="sxs-lookup"><span data-stu-id="3f85c-429">A client can look for the presence of the flag to decide whether to request or to save Unicode information to the store.</span></span>  <br/> |
   
### <a name="definitions-for-archiving-items-in-a-folder"></a><span data-ttu-id="3f85c-430">在文件夹中存档项目的定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-430">Definitions for archiving items in a folder</span></span>

<span data-ttu-id="3f85c-431">以下常量定义是用于设置 [PidTagAgingGranularity 规范属性](pidtagaginggranularity-canonical-property.md)的值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-431">The following constant definitions are values used to set the [PidTagAgingGranularity Canonical Property](pidtagaginggranularity-canonical-property.md).</span></span>
  
```cpp
#define AG_MONTHS 0 
#define AG_WEEKS  1 
#define AG_DAYS   2 

```

### <a name="definitions-for-displaying-remote-objects"></a><span data-ttu-id="3f85c-432">显示远程对象的定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-432">Definitions for displaying remote objects</span></span>

<span data-ttu-id="3f85c-433">以下常量和宏定义用于显示远程对象。</span><span class="sxs-lookup"><span data-stu-id="3f85c-433">The following constant and macro definitions are for displaying remote objects.</span></span> <span data-ttu-id="3f85c-434">有关详细信息，请参阅 [PidTagDisplayTypeEx 规范属性](pidtagdisplaytypeex-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="3f85c-434">For more information, see the [PidTagDisplayTypeEx Canonical Property](pidtagdisplaytypeex-canonical-property.md).</span></span>
  
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

### <a name="definitions-for-exchange-address-book-and-message-store-error-codes"></a><span data-ttu-id="3f85c-435">Exchange 通讯簿和邮件存储错误代码定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-435">Definitions for Exchange address book and Message store error codes</span></span>

<span data-ttu-id="3f85c-436">下列包含 Exchange 通讯簿以及邮件存储的错误代码定义，它们具有重新连接功能。</span><span class="sxs-lookup"><span data-stu-id="3f85c-436">The following contains error code definitions for the Exchange Address Book and Message Store, which have reconnection capability.</span></span> <span data-ttu-id="3f85c-437">对断开连接的全局编录 (GC) 的最后一次调用可能会导致 **MAPI_E_END_OF_SESSION** 错误，可能需要重试。</span><span class="sxs-lookup"><span data-stu-id="3f85c-437">The last call to a disconnected Global Catalog (GC) may result in the **MAPI_E_END_OF_SESSION** error, which would need to be retried.</span></span> 
  
<span data-ttu-id="3f85c-438">Outlook 的 MAPI 支持重新连接到 GC 服务器，而不需要特殊的重新配置，但是一些其他错误代码可以返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="3f85c-438">Outlook's MAPI supports reconnection to a GC server without special reconfiguration, but some other error codes can be returned to the client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3f85c-439">MAPI_E_END_OF_SESSION</span><span class="sxs-lookup"><span data-stu-id="3f85c-439">MAPI_E_END_OF_SESSION</span></span>  <br/> |<span data-ttu-id="3f85c-440">0x80040200</span><span class="sxs-lookup"><span data-stu-id="3f85c-440">0x80040200</span></span>  <br/> |<span data-ttu-id="3f85c-441">断开连接时返回。</span><span class="sxs-lookup"><span data-stu-id="3f85c-441">Returned when a connection has been disconnected.</span></span>  <br/> |
|<span data-ttu-id="3f85c-442">MAPI_E_RECONNECTED</span><span class="sxs-lookup"><span data-stu-id="3f85c-442">MAPI_E_RECONNECTED</span></span>  <br/> |<span data-ttu-id="3f85c-443">0x80040125</span><span class="sxs-lookup"><span data-stu-id="3f85c-443">0x80040125</span></span>  <br/> |<span data-ttu-id="3f85c-444">在远程过程调用 (RPC) 连接令牌过期时返回。</span><span class="sxs-lookup"><span data-stu-id="3f85c-444">Returned when the Remote Procedure Call (RPC) connection token is out-of-date.</span></span> <span data-ttu-id="3f85c-445">如果当前事务的令牌不同于连接令牌，则意味着它已重新连接，因此将返回 **MAPI_E_RECONNECTED**，且可以作为相同的 **MAPI_E_END_OF_SESSION** 处理。</span><span class="sxs-lookup"><span data-stu-id="3f85c-445">If the token of the current transaction is different from the token of the connection that means it has reconnected, so **MAPI_E_RECONNECTED** is returned and can be treated the same as **MAPI_E_END_OF_SESSION**.</span></span> <span data-ttu-id="3f85c-446">应重试调用。</span><span class="sxs-lookup"><span data-stu-id="3f85c-446">The call should be retried.</span></span>  <br/> |
|<span data-ttu-id="3f85c-447">MAPI_E_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="3f85c-447">MAPI_E_OFFLINE</span></span>  <br/> |<span data-ttu-id="3f85c-448">0x80040126</span><span class="sxs-lookup"><span data-stu-id="3f85c-448">0x80040126</span></span>  <br/> |<span data-ttu-id="3f85c-449">连接处于脱机状态时返回。</span><span class="sxs-lookup"><span data-stu-id="3f85c-449">Returned when the connection is offline.</span></span> <span data-ttu-id="3f85c-450">通常情况下，这意味着环境中出现了一些状况，比如服务器故障或网络连接丢失。</span><span class="sxs-lookup"><span data-stu-id="3f85c-450">Typically this means that something has occurred in the environment, such as server failure or loss of network connectivity.</span></span> <span data-ttu-id="3f85c-451">该错误最有可能在使用缓存模式配置文件和尝试绕过缓存与服务器通信时发生。</span><span class="sxs-lookup"><span data-stu-id="3f85c-451">This error is most likely to occur when using a cached mode profile and attempting to bypass the cache to communicate with the server.</span></span> <span data-ttu-id="3f85c-452">如果缓存无法初始建立到服务器的连接，它可能处于脱机状态，其中可能会显示 **MAPI_E_OFFLINE**。</span><span class="sxs-lookup"><span data-stu-id="3f85c-452">If the cache was never able to initially establish a connection to the server, it may be in the offline state in which **MAPI_E_OFFLINE** could surface.</span></span>  <br/> |
   
<span data-ttu-id="3f85c-453">在所有可能出现的场景中，前两个错误都不会返回。</span><span class="sxs-lookup"><span data-stu-id="3f85c-453">Neither of the preceding two errors will be returned in all scenarios where they would likely appear to apply.</span></span> <span data-ttu-id="3f85c-454">大多数情况下，将返回 **MAPI\_E_NETWORK_ERROR** 或 **MAPI_E_CALL_FAILED**。</span><span class="sxs-lookup"><span data-stu-id="3f85c-454">In most cases, **MAPI\_E_NETWORK_ERROR** or **MAPI_E_CALL_FAILED** will be returned.</span></span> <span data-ttu-id="3f85c-455">使用 [Microsoft Exchange Server MAPI 客户端和协作数据对象 1.2.1](http://support.microsoft.com/kb/171440) 下载，两者都不会出现。</span><span class="sxs-lookup"><span data-stu-id="3f85c-455">Neither will appear using the [Microsoft Exchange Server MAPI Client and Collaboration Data Objects 1.2.1](http://support.microsoft.com/kb/171440) download.</span></span> 
  
### <a name="definitions-for-exchange-server-mailbox-cached-mode-quotas"></a><span data-ttu-id="3f85c-456">Exchange 服务器邮箱缓存模式配额的定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-456">Definitions for Exchange Server Mailbox cached mode quotas</span></span>

<span data-ttu-id="3f85c-457">Microsoft Outlook 2010 和 Microsoft Outlook 2013 使用以下常量定义来设置 Exchange 缓存模式配置文件配额，该配额等同于 Exchange 邮箱配额，只不过只有在使用联机配置文件时才提供。</span><span class="sxs-lookup"><span data-stu-id="3f85c-457">The following constant definitions are used by Microsoft Outlook 2010 and Microsoft Outlook 2013 to set the Exchange cached mode profile quotas that are equivalent to the Exchange mailbox quotas otherwise available only with an online profile.</span></span>
  
```cpp
#define PR_QUOTA_WARNING PROP_TAG( PT_LONG, 0x341A)
#define PR_QUOTA_SEND    PROP_TAG( PT_LONG, 0x341B)
#define PR_QUOTA_RECEIVE PROP_TAG( PT_LONG, 0x341C)
```

<span data-ttu-id="3f85c-458">这些属性映射到其对应的联机属性并包含以千字节为单位的相同值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-458">These properties map to their correspondent online properties and contain the same values in kilobytes.</span></span> <span data-ttu-id="3f85c-459">PR_QUOTA_WARNING 映射到 PR_STORAGE_QUOTA_LIMIT，PR_QUOTA_SEND 映射到 PR_QUOTA_PROHIBIT_SEND_QUOTA，以及 PR_QUOTA_RECEIVE 映射到 PR_PROHIBIT_RECEIVE_QUOTA。</span><span class="sxs-lookup"><span data-stu-id="3f85c-459">PR_QUOTA_WARNING maps to PR_STORAGE_QUOTA_LIMIT, PR_QUOTA_SEND to PR_QUOTA_PROHIBIT_SEND_QUOTA, and PR_QUOTA_RECEIVE to PR_PROHIBIT_RECEIVE_QUOTA.</span></span>
  
### <a name="definitions-for-message-format"></a><span data-ttu-id="3f85c-460">邮件格式定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-460">Definitions for message format</span></span>

<span data-ttu-id="3f85c-461">以下常量定义是用于设置 [PidTagMessageEditorFormat 规范属性](pidtagmessageeditorformat-canonical-property.md)的值。</span><span class="sxs-lookup"><span data-stu-id="3f85c-461">The following constant definitions are values that are used to set the [PidTagMessageEditorFormat Canonical Property](pidtagmessageeditorformat-canonical-property.md).</span></span>
  
```cpp
#define EDITOR_FORMAT_DONTKNOW  ((ULONG) 0) 
#define EDITOR_FORMAT_PLAINTEXT ((ULONG) 1) 
#define EDITOR_FORMAT_HTML      ((ULONG) 2) 
#define EDITOR_FORMAT_RTF       ((ULONG) 3)
```

### <a name="definitions-for-using-rpc-over-http"></a><span data-ttu-id="3f85c-462">通过 HTTP 使用 RPC 的定义</span><span class="sxs-lookup"><span data-stu-id="3f85c-462">Definitions for using RPC over HTTP</span></span>

<span data-ttu-id="3f85c-463">有关用作标记来设置属性的常量定义，请参阅 [PidTagRpcOverHttpFlags 规范属性](pidtagrpcoverhttpflags-canonical-property.md)主题。</span><span class="sxs-lookup"><span data-stu-id="3f85c-463">See the [PidTagRpcOverHttpFlags Canonical Property](pidtagrpcoverhttpflags-canonical-property.md) topic for constant definitions used as flags to set the property.</span></span> 
  
<span data-ttu-id="3f85c-464">有关用于设置属性的常量定义，请参阅 [PidTagRpcOverHttpProxyAuthScheme 规范属性](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)主题。</span><span class="sxs-lookup"><span data-stu-id="3f85c-464">See the [PidTagRpcOverHttpProxyAuthScheme Canonical Property](pidtagrpcoverhttpproxyauthscheme-canonical-property.md) topic for constant definitions used to set the property.</span></span> 
  
### <a name="identifiers"></a><span data-ttu-id="3f85c-465">标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-465">Identifiers</span></span>

<span data-ttu-id="3f85c-466">使用在 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 `DEFINE_OLEGUID` 宏，将以下 GUID 符号名称与其值关联起来。</span><span class="sxs-lookup"><span data-stu-id="3f85c-466">Use the  `DEFINE_OLEGUID` macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate the following GUID symbolic names with their values.</span></span> 
  
```cpp
//{0002038A-0000-0000-C000-000000000046}
#if !defined(INITGUID) || defined(USES_IID_IMessageRaw) 
DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0); 
#endif
```

<span data-ttu-id="3f85c-467">下列标识符用于通讯簿的 Capone 配置文件部分，它支持多个 Exchange ([MultiEx](using-multiple-exchange-accounts.md)) 邮箱，包含一个 [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) 属性，以便有效地关闭由 [SetDefaultDir](iaddrbook-setdefaultdir.md) 指定的默认容器。</span><span class="sxs-lookup"><span data-stu-id="3f85c-467">The following Identifier is for the Capone Profile section of an Address Book, which in support of multiple Exchange ([MultiEx](using-multiple-exchange-accounts.md)) mailboxes contains a [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property that effectively turns off the default container specified by [SetDefaultDir](iaddrbook-setdefaultdir.md).</span></span>
  
```cpp
// {00020D0A-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_CAPONE_PROF, 0x00020d0a, 0, 0);
```

### <a name="interface-identifiers"></a><span data-ttu-id="3f85c-468">接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-468">Interface identifiers</span></span>

#### <a name="imapisync"></a><span data-ttu-id="3f85c-469">IMAPISync</span><span class="sxs-lookup"><span data-stu-id="3f85c-469">IMAPISync : SynchronizeInBackground</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISync, 0x5024a385, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);

```

#### <a name="imapisyncprogresscallback"></a><span data-ttu-id="3f85c-470">IMAPISyncProgressCallback</span><span class="sxs-lookup"><span data-stu-id="3f85c-470">IMAPISyncProgressCallback::Done</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISyncProgressCallback, 0x5024a386, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);
```

#### <a name="iidicontabadmin"></a><span data-ttu-id="3f85c-471">IID_IContabAdmin</span><span class="sxs-lookup"><span data-stu-id="3f85c-471">IID_IContabAdmin</span></span>
  
```cpp
// {CC6A3BA9-E7F5-4769-887B-34E190817BFC}
DEFINE_GUID(IID_IContabAdmin, 0xcc6a3ba9, 0xe7f5, 0x4769, 0x88, 0x7b, 0x34, 0xe1, 0x90, 0x81, 0x7b, 0xfc);

```

#### <a name="iidimapisecuremessage"></a><span data-ttu-id="3f85c-472">IID_IMAPISECUREMESSAGE</span><span class="sxs-lookup"><span data-stu-id="3f85c-472">IID_IMAPISECUREMESSAGE</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISecureMessage, 0x253cc320, 0xeab6, 0x11d0, 0x82, 0x22, 0, 0x60, 0x97, 0x93, 0x87, 0xea);

```

#### <a name="iidimapigetsession"></a><span data-ttu-id="3f85c-473">IID_IMAPIGetSession</span><span class="sxs-lookup"><span data-stu-id="3f85c-473">IID_IMAPIGetSession</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPIGetSession, 0x614ab435, 0x491d, 0x4f5b, 0xa8, 0xb4, 0x60, 0xeb, 0x3, 0x10, 0x30, 0xc6);

```

### <a name="pst-override-handler-interface-identifiers"></a><span data-ttu-id="3f85c-474">PST 重写处理程序接口标识符</span><span class="sxs-lookup"><span data-stu-id="3f85c-474">PST Override Handler interface identifiers</span></span>

#### <a name="iidipstoverridereq"></a><span data-ttu-id="3f85c-475">IID_IPSTOVERRIDEREQ</span><span class="sxs-lookup"><span data-stu-id="3f85c-475">IID_IPSTOVERRIDEREQ</span></span>
  
```cpp
// {892EBC6D-24DC-4d90-BA48-C6CBEC14A86A}
DEFINE_GUID(IID_IPSTOVERRIDEREQ, 0x892ebc6d, 0x24dc, 0x4d90, 0xba, 0x48, 0xc6, 0xcb, 0xec, 0x14, 0xa8, 0x6a);
```

#### <a name="iidipstoverride1"></a><span data-ttu-id="3f85c-476">IID_IPSTOVERRIDE1</span><span class="sxs-lookup"><span data-stu-id="3f85c-476">IID_IPSTOVERRIDE1</span></span>
  
```cpp
// {FBB68D34-F561-44fb-A8CA-AE36696342CA}
DEFINE_GUID(IID_IPSTOVERRIDE1, 0xfbb68d34, 0xf561, 0x44fb, 0xa8, 0xca, 0xae, 0x36, 0x69, 0x63, 0x42, 0xca);
```

## <a name="see-also"></a><span data-ttu-id="3f85c-477">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f85c-477">See also</span></span>

- [<span data-ttu-id="3f85c-478">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="3f85c-478">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="3f85c-479">关于 Outlook 使用的命名属性</span><span class="sxs-lookup"><span data-stu-id="3f85c-479">About Named Properties Used by Outlook</span></span>](about-named-properties-used-by-outlook.md)
- [<span data-ttu-id="3f85c-480">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="3f85c-480">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="3f85c-481">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="3f85c-481">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="3f85c-482">在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）</span><span class="sxs-lookup"><span data-stu-id="3f85c-482">Manage a Message in an OST Without Invoking a Synchronization in Cached Exchange Mode</span></span>](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

