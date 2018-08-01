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
# <a name="mapi-constants"></a><span data-ttu-id="dd148-103">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="dd148-103">MAPI constants</span></span>

<span data-ttu-id="dd148-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dd148-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dd148-105">本主题包含常量定义、 MAPI 接口声明和 MAPI Api 使用的类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="dd148-105">This topic contains constant definitions, MAPI interface declarations, and class and interface identifiers used by the MAPI APIs.</span></span>
  
## <a name="class-and-interface-identifiers"></a><span data-ttu-id="dd148-106">类和接口标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-106">Class and interface identifiers</span></span>

<span data-ttu-id="dd148-107">使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 的符号名称相关联的值，除非另有说明。</span><span class="sxs-lookup"><span data-stu-id="dd148-107">Use the DEFINE_GUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate globally unique identifier (GUID) symbolic names with their values, unless otherwise indicated.</span></span>
  
## <a name="attachment-security-conversion-api"></a><span data-ttu-id="dd148-108">附件安全转换 API</span><span class="sxs-lookup"><span data-stu-id="dd148-108">Attachment security conversion API</span></span>

<span data-ttu-id="dd148-109">此部分包含附件安全 api 常量定义和界面标识符。</span><span class="sxs-lookup"><span data-stu-id="dd148-109">This section contains constant definitions and interface identifiers for the Attachment Security API.</span></span>
  
```cpp
// {b2533636-c3f3-416f-bf04-aefe41abaae2}
DEFINE_GUID(IID_IAttachmentSecurity, 0xb2533636, 0xc3f3, 0x416f, 0xbf, 0x04, 0xae, 0xfe, 0x41, 0xab, 0xaa, 0xe2);
```

<span data-ttu-id="dd148-110">使用 Windows SDK 标头文件 mapidefs.h 中定义的 MAPIMETHOD 宏定义纯虚函数**[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**。</span><span class="sxs-lookup"><span data-stu-id="dd148-110">Use the MAPIMETHOD macro defined in the Windows SDK header file mapidefs.h to define the pure virtual function **[IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)**.</span></span> 
  
```cpp
#define MAPI_IATTACHMENTSECURITY_METHODS(IPURE)         MAPIMETHOD(IsAttachmentBlocked)         (LPCWSTR pwszFileName, BOOL *pfBlocked) IPURE;
```

<span data-ttu-id="dd148-111">使用 Windows SDK 标头文件 mapidefs.h 中定义 DECLARE_MAPI_INTERFACE_ 宏以定义**[IAttachmentSecurity](iattachmentsecurityiunknown.md)** 虚拟方法表。</span><span class="sxs-lookup"><span data-stu-id="dd148-111">Use the DECLARE_MAPI_INTERFACE_ macro defined in the Windows SDK header file mapidefs.h to define the virtual method table for **[IAttachmentSecurity](iattachmentsecurityiunknown.md)**.</span></span> 
  
```cpp
DECLARE_MAPI_INTERFACE_(IAttachmentSecurity, IUnknown) 
{ 
    BEGIN_INTERFACE 
    MAPI_IUNKNOWN_METHODS(PURE) 
    MAPI_IATTACHMENTSECURITY_METHODS(PURE) 
};
```

## <a name="mapi-mime-conversion-api"></a><span data-ttu-id="dd148-112">MAPI MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="dd148-112">MAPI-MIME conversion API</span></span>

<span data-ttu-id="dd148-113">本节包含对 MAPI MIME 转换 API 常量定义和类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="dd148-113">This section contains constant definitions and class and interface identifiers for the MAPI-MIME Conversion API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="dd148-114">常量</span><span class="sxs-lookup"><span data-stu-id="dd148-114">Constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dd148-115">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="dd148-115">CCSF_SMTP</span></span>  <br/> |<span data-ttu-id="dd148-116">0x0002</span><span class="sxs-lookup"><span data-stu-id="dd148-116">0x0002</span></span>  <br/> |
|<span data-ttu-id="dd148-117">CCSF_NOHEADERS</span><span class="sxs-lookup"><span data-stu-id="dd148-117">CCSF_NOHEADERS</span></span>  <br/> |<span data-ttu-id="dd148-118">0x0004</span><span class="sxs-lookup"><span data-stu-id="dd148-118">0x0004</span></span>  <br/> |
|<span data-ttu-id="dd148-119">CCSF_USE_TNEF</span><span class="sxs-lookup"><span data-stu-id="dd148-119">CCSF_USE_TNEF</span></span>  <br/> | <span data-ttu-id="dd148-120">0x0010</span><span class="sxs-lookup"><span data-stu-id="dd148-120">0x0010</span></span>  <br/> |
|<span data-ttu-id="dd148-121">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="dd148-121">CCSF_INCLUDE_BCC</span></span>  <br/> |<span data-ttu-id="dd148-122">0x0020</span><span class="sxs-lookup"><span data-stu-id="dd148-122">0x0020</span></span>  <br/> |
|<span data-ttu-id="dd148-123">CCSF_8BITHEADERS</span><span class="sxs-lookup"><span data-stu-id="dd148-123">CCSF_8BITHEADERS</span></span>  <br/> | <span data-ttu-id="dd148-124">0x0040</span><span class="sxs-lookup"><span data-stu-id="dd148-124">0x0040</span></span>  <br/> |
|<span data-ttu-id="dd148-125">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="dd148-125">CCSF_USE_RTF</span></span>  <br/> |<span data-ttu-id="dd148-126">0x0080</span><span class="sxs-lookup"><span data-stu-id="dd148-126">0x0080</span></span>  <br/> |
|<span data-ttu-id="dd148-127">CCSF_PLAIN_TEXT_ONLY</span><span class="sxs-lookup"><span data-stu-id="dd148-127">CCSF_PLAIN_TEXT_ONLY</span></span>  <br/> |<span data-ttu-id="dd148-128">0x1000</span><span class="sxs-lookup"><span data-stu-id="dd148-128">0x1000</span></span>  <br/> |
|<span data-ttu-id="dd148-129">CCSF_NO_MSGID</span><span class="sxs-lookup"><span data-stu-id="dd148-129">CCSF_NO_MSGID</span></span>  <br/> |<span data-ttu-id="dd148-130">0x4000</span><span class="sxs-lookup"><span data-stu-id="dd148-130">0x4000</span></span>  <br/> |
|<span data-ttu-id="dd148-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dd148-131">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="dd148-132">*Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义*</span><span class="sxs-lookup"><span data-stu-id="dd148-132">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h*</span></span>  <br/> |
   
### <a name="class-identifiers"></a><span data-ttu-id="dd148-133">类标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-133">Class identifiers</span></span>

```cpp
// {4e3a7680-b77a-11d0-9da5-00c04fd65685}
DEFINE_GUID(CLSID_IConverterSession, 0x4e3a7680, 0xb77a, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

### <a name="interface-identifiers"></a><span data-ttu-id="dd148-134">界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-134">Interface identifiers</span></span>

```cpp
// {4b401570-b77b-11d0-9da5-00c04fd65685}
DEFINE_GUID(IID_IConverterSession, 0x4b401570, 0xb77b, 0x11d0, 0x9d, 0xa5, 0x0, 0xc0, 0x4f, 0xd6, 0x56, 0x85);
```

## <a name="offline-state-api"></a><span data-ttu-id="dd148-135">脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="dd148-135">Offline State API</span></span>

<span data-ttu-id="dd148-136">此部分包含脱机状态 api 常量定义和类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="dd148-136">This section contains constant definitions and class and interface identifiers for the Offline State API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="dd148-137">常量</span><span class="sxs-lookup"><span data-stu-id="dd148-137">Constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dd148-138">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dd148-138">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="dd148-139">*Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义*</span><span class="sxs-lookup"><span data-stu-id="dd148-139">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h*</span></span>  <br/> |
|<span data-ttu-id="dd148-140">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="dd148-140">E_NOINTERFACE</span></span>  <br/> | <span data-ttu-id="dd148-141">*在 Windows (SDK) 标头文件 winerror.h 中定义*</span><span class="sxs-lookup"><span data-stu-id="dd148-141">*As defined in the Windows (SDK) header file winerror.h*</span></span>  <br/> |
|<span data-ttu-id="dd148-142">MAPIOFFLINE_ADVISE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="dd148-142">MAPIOFFLINE_ADVISE_DEFAULT</span></span>  <br/> |<span data-ttu-id="dd148-143">满足） 0</span><span class="sxs-lookup"><span data-stu-id="dd148-143">(ULONG)0</span></span>  <br/> |
|<span data-ttu-id="dd148-144">MAPIOFFLINE_UNADVISE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="dd148-144">MAPIOFFLINE_UNADVISE_DEFAULT</span></span>  <br/> |<span data-ttu-id="dd148-145">满足） 0</span><span class="sxs-lookup"><span data-stu-id="dd148-145">(ULONG)0</span></span>  <br/> |
|<span data-ttu-id="dd148-146">MAPIOFFLINE_ADVISE_TYPE_STATECHANGE</span><span class="sxs-lookup"><span data-stu-id="dd148-146">MAPIOFFLINE_ADVISE_TYPE_STATECHANGE</span></span>  <br/> |<span data-ttu-id="dd148-147">1</span><span class="sxs-lookup"><span data-stu-id="dd148-147">1</span></span>  <br/> |
|<span data-ttu-id="dd148-148">MAPIOFFLINE_CAPABILITY_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-148">MAPIOFFLINE_CAPABILITY_OFFLINE</span></span>  <br/> |<span data-ttu-id="dd148-149">0x1</span><span class="sxs-lookup"><span data-stu-id="dd148-149">0x1</span></span>  <br/> |
|<span data-ttu-id="dd148-150">MAPIOFFLINE_CAPABILITY_ONLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-150">MAPIOFFLINE_CAPABILITY_ONLINE</span></span>  <br/> |<span data-ttu-id="dd148-151">0x2</span><span class="sxs-lookup"><span data-stu-id="dd148-151">0x2</span></span>  <br/> |
|<span data-ttu-id="dd148-152">MAPIOFFLINE_FLAG_BLOCK</span><span class="sxs-lookup"><span data-stu-id="dd148-152">MAPIOFFLINE_FLAG_BLOCK</span></span>  <br/> |<span data-ttu-id="dd148-153">0x00002000</span><span class="sxs-lookup"><span data-stu-id="dd148-153">0x00002000</span></span>  <br/> |
|<span data-ttu-id="dd148-154">MAPIOFFLINE_FLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="dd148-154">MAPIOFFLINE_FLAG_DEFAULT</span></span>  <br/> |<span data-ttu-id="dd148-155">0x00000000</span><span class="sxs-lookup"><span data-stu-id="dd148-155">0x00000000</span></span>  <br/> |
|<span data-ttu-id="dd148-156">MAPIOFFLINE_STATE_ALL</span><span class="sxs-lookup"><span data-stu-id="dd148-156">MAPIOFFLINE_STATE_ALL</span></span>  <br/> |<span data-ttu-id="dd148-157">0x003f037f</span><span class="sxs-lookup"><span data-stu-id="dd148-157">0x003f037f</span></span>  <br/> |
|<span data-ttu-id="dd148-158">**联机或脱机**</span><span class="sxs-lookup"><span data-stu-id="dd148-158">**Online or offline**</span></span> <br/> ||
|<span data-ttu-id="dd148-159">MAPIOFFLINE_STATE_OFFLINE_MASK</span><span class="sxs-lookup"><span data-stu-id="dd148-159">MAPIOFFLINE_STATE_OFFLINE_MASK</span></span>  <br/> |<span data-ttu-id="dd148-160">0x00000003</span><span class="sxs-lookup"><span data-stu-id="dd148-160">0x00000003</span></span>  <br/> |
|<span data-ttu-id="dd148-161">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-161">MAPIOFFLINE_STATE_OFFLINE</span></span>  <br/> |<span data-ttu-id="dd148-162">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-162">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-163">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-163">MAPIOFFLINE_STATE_ONLINE</span></span>  <br/> |<span data-ttu-id="dd148-164">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-164">0x00000002</span></span>  <br/> |
   
### <a name="class-identifiers"></a><span data-ttu-id="dd148-165">类标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-165">Class identifiers</span></span>

```cpp
//{fbeffd93-b11f-4094-842b-96dcd31e63d1}
DEFINE_GUID(GUID_GlobalState, 0xfbeffd93, 0xb11f, 0x4094, 0x84, 0x2b, 0x96, 0xdc, 0xd3, 0x1e, 0x63, 0xd1);
```

### <a name="interface-identifiers"></a><span data-ttu-id="dd148-166">界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-166">Interface identifiers</span></span>

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

## <a name="outlook-named-properties"></a><span data-ttu-id="dd148-167">Outlook 命名属性</span><span class="sxs-lookup"><span data-stu-id="dd148-167">Outlook named properties</span></span>

<span data-ttu-id="dd148-168">此部分包含常量定义的命名属性的命名空间引用和其他相关的常量。</span><span class="sxs-lookup"><span data-stu-id="dd148-168">This section contains constant definitions for named properties and their namespaces, and other related constants.</span></span>
  
### <a name="definitions-for-named-properties"></a><span data-ttu-id="dd148-169">定义命名属性</span><span class="sxs-lookup"><span data-stu-id="dd148-169">Definitions for named properties</span></span>

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

### <a name="definitions-for-namespaces"></a><span data-ttu-id="dd148-170">定义命名空间</span><span class="sxs-lookup"><span data-stu-id="dd148-170">Definitions for namespaces</span></span>

<span data-ttu-id="dd148-171">以下全局唯一标识符 (Guid) 表示的命名属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="dd148-171">The following globally unique identifiers (GUIDs) represent the namespaces of the named properties.</span></span>
  
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

<span data-ttu-id="dd148-172">请参阅 PSETID 定义的 MAPI 存储一节。</span><span class="sxs-lookup"><span data-stu-id="dd148-172">Refer to the section MAPI Store for the PSETID definitions.</span></span>
  
### <a name="other-constants"></a><span data-ttu-id="dd148-173">其他常量</span><span class="sxs-lookup"><span data-stu-id="dd148-173">Other constants</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dd148-174">INSP_ONEOFFFLAGS</span><span class="sxs-lookup"><span data-stu-id="dd148-174">INSP_ONEOFFFLAGS</span></span>  <br/> |<span data-ttu-id="dd148-175">0xD000000</span><span class="sxs-lookup"><span data-stu-id="dd148-175">0xD000000</span></span>  <br/> |
|<span data-ttu-id="dd148-176">INSP_PROPDEFINITION</span><span class="sxs-lookup"><span data-stu-id="dd148-176">INSP_PROPDEFINITION</span></span>  <br/> |<span data-ttu-id="dd148-177">0x2000000</span><span class="sxs-lookup"><span data-stu-id="dd148-177">0x2000000</span></span>  <br/> |
|<span data-ttu-id="dd148-178">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="dd148-178">MNID_ID</span></span>  <br/> | <span data-ttu-id="dd148-179">*标头文件 mapidefs.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="dd148-179">*As defined in the header file mapidefs.h.*</span></span>  <br/> |
|<span data-ttu-id="dd148-180">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="dd148-180">MNID_STRING</span></span>  <br/> | <span data-ttu-id="dd148-181">*标头文件 mapidefs.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="dd148-181">*As defined in the header file mapidefs.h.*</span></span>  <br/> |
|<span data-ttu-id="dd148-182">mtgNone</span><span class="sxs-lookup"><span data-stu-id="dd148-182">mtgNone</span></span>  <br/> |<span data-ttu-id="dd148-183">0x0</span><span class="sxs-lookup"><span data-stu-id="dd148-183">0x0</span></span>  <br/> |
|<span data-ttu-id="dd148-184">mtgRequest</span><span class="sxs-lookup"><span data-stu-id="dd148-184">mtgRequest</span></span>  <br/> |<span data-ttu-id="dd148-185">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-185">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-186">mtgFullUpdate</span><span class="sxs-lookup"><span data-stu-id="dd148-186">mtgFullUpdate</span></span>  <br/> |<span data-ttu-id="dd148-187">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-187">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-188">mtgInfoUpdate</span><span class="sxs-lookup"><span data-stu-id="dd148-188">mtgInfoUpdate</span></span>  <br/> |<span data-ttu-id="dd148-189">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-189">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-190">mtgOutofDate</span><span class="sxs-lookup"><span data-stu-id="dd148-190">mtgOutofDate</span></span>  <br/> |<span data-ttu-id="dd148-191">0x00080000</span><span class="sxs-lookup"><span data-stu-id="dd148-191">0x00080000</span></span>  <br/> |
|<span data-ttu-id="dd148-192">mtgDelegated</span><span class="sxs-lookup"><span data-stu-id="dd148-192">mtgDelegated</span></span>  <br/> |<span data-ttu-id="dd148-193">0x00100000</span><span class="sxs-lookup"><span data-stu-id="dd148-193">0x00100000</span></span>  <br/> |
   
## <a name="replication-api"></a><span data-ttu-id="dd148-194">复制 API</span><span class="sxs-lookup"><span data-stu-id="dd148-194">Replication API</span></span>

<span data-ttu-id="dd148-195">此部分包含有关复制 API 常量定义、 MAPI 接口声明和类和接口标识符。</span><span class="sxs-lookup"><span data-stu-id="dd148-195">This section contains constant definitions, MAPI interface declarations, and class and interface identifiers for the Replication API.</span></span>
  
### <a name="constants"></a><span data-ttu-id="dd148-196">常量</span><span class="sxs-lookup"><span data-stu-id="dd148-196">Constants</span></span>

<span data-ttu-id="dd148-197">以下是标识 MAPI 服务提供商[MAPIUID](mapiuid.md)结构：</span><span class="sxs-lookup"><span data-stu-id="dd148-197">The following is a [MAPIUID](mapiuid.md) structure identifying a MAPI service provider:</span></span> 
  
```cpp
const MAPIUID g_muidProvPrvNST = 
 { 0xE9, 0x2F, 0xEB, 0x75, 0x96, 0x50, 0x44, 0x86, 
      0x83, 0xB8, 0x7D, 0xE5, 0x22, 0xAA, 0x49, 0x48 };
```

|||
|:-----|:-----|
|<span data-ttu-id="dd148-198">DNH_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-198">DNH_OK</span></span>  <br/> |<span data-ttu-id="dd148-199">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-199">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-200">DNT_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-200">DNT_OK</span></span>  <br/> |<span data-ttu-id="dd148-201">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-201">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-202">HSF_LOCAL</span><span class="sxs-lookup"><span data-stu-id="dd148-202">HSF_LOCAL</span></span>  <br/> |<span data-ttu-id="dd148-203">0x00000008</span><span class="sxs-lookup"><span data-stu-id="dd148-203">0x00000008</span></span>  <br/> |
|<span data-ttu-id="dd148-204">HSF_COPYDESTRUCTIVE</span><span class="sxs-lookup"><span data-stu-id="dd148-204">HSF_COPYDESTRUCTIVE</span></span>  <br/> |<span data-ttu-id="dd148-205">0x00000010</span><span class="sxs-lookup"><span data-stu-id="dd148-205">0x00000010</span></span>  <br/> |
|<span data-ttu-id="dd148-206">HSF_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-206">HSF_OK</span></span>  <br/> |<span data-ttu-id="dd148-207">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-207">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-208">MDB_OST_LOGON_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dd148-208">MDB_OST_LOGON_UNICODE</span></span>  <br/> |<span data-ttu-id="dd148-209">（满足） 0X00000800）</span><span class="sxs-lookup"><span data-stu-id="dd148-209">((ULONG) 0x00000800)</span></span>  <br/> |
|<span data-ttu-id="dd148-210">MDB_OST_LOGON_ANSI</span><span class="sxs-lookup"><span data-stu-id="dd148-210">MDB_OST_LOGON_ANSI</span></span>  <br/> |<span data-ttu-id="dd148-211">（满足） 0X00001000）</span><span class="sxs-lookup"><span data-stu-id="dd148-211">((ULONG) 0x00001000)</span></span>  <br/> |
|<span data-ttu-id="dd148-212">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="dd148-212">SHOW_SOFT_DELETES</span></span>  <br/> |<span data-ttu-id="dd148-213">（满足） 0X00000002:UC）</span><span class="sxs-lookup"><span data-stu-id="dd148-213">((ULONG) 0x00000002)</span></span>  <br/> |
|<span data-ttu-id="dd148-214">SS_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="dd148-214">SS_ACTIVE</span></span>  <br/> |<span data-ttu-id="dd148-215">0</span><span class="sxs-lookup"><span data-stu-id="dd148-215">0</span></span>  <br/> |
|<span data-ttu-id="dd148-216">SS_SUSPENDED</span><span class="sxs-lookup"><span data-stu-id="dd148-216">SS_SUSPENDED</span></span>  <br/> |<span data-ttu-id="dd148-217">1</span><span class="sxs-lookup"><span data-stu-id="dd148-217">1</span></span>  <br/> |
|<span data-ttu-id="dd148-218">SYNC_UPLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="dd148-218">SYNC_UPLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="dd148-219">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-219">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-220">SYNC_DOWNLOAD_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="dd148-220">SYNC_DOWNLOAD_HIERARCHY</span></span>  <br/> |<span data-ttu-id="dd148-221">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-221">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-222">SYNC_UPLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="dd148-222">SYNC_UPLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="dd148-223">0x00000040</span><span class="sxs-lookup"><span data-stu-id="dd148-223">0x00000040</span></span>  <br/> |
|<span data-ttu-id="dd148-224">SYNC_DOWNLOAD_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="dd148-224">SYNC_DOWNLOAD_CONTENTS</span></span>  <br/> |<span data-ttu-id="dd148-225">0x00000080</span><span class="sxs-lookup"><span data-stu-id="dd148-225">0x00000080</span></span>  <br/> |
|<span data-ttu-id="dd148-226">SYNC_OUTGOING_MAIL</span><span class="sxs-lookup"><span data-stu-id="dd148-226">SYNC_OUTGOING_MAIL</span></span>  <br/> |<span data-ttu-id="dd148-227">0x00000200</span><span class="sxs-lookup"><span data-stu-id="dd148-227">0x00000200</span></span>  <br/> |
|<span data-ttu-id="dd148-228">SYNC_BACKGROUND</span><span class="sxs-lookup"><span data-stu-id="dd148-228">SYNC_BACKGROUND</span></span>  <br/> |<span data-ttu-id="dd148-229">0x00001000</span><span class="sxs-lookup"><span data-stu-id="dd148-229">0x00001000</span></span>  <br/> |
|<span data-ttu-id="dd148-230">SYNC_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="dd148-230">SYNC_THESE_FOLDERS</span></span>  <br/> |<span data-ttu-id="dd148-231">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-231">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-232">SYNC_HEADERS</span><span class="sxs-lookup"><span data-stu-id="dd148-232">SYNC_HEADERS</span></span>  <br/> |<span data-ttu-id="dd148-233">0x02000000</span><span class="sxs-lookup"><span data-stu-id="dd148-233">0x02000000</span></span>  <br/> |
|<span data-ttu-id="dd148-234">UPC_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-234">UPC_OK</span></span>  <br/> |<span data-ttu-id="dd148-235">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-235">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-236">UPD_ASSOC</span><span class="sxs-lookup"><span data-stu-id="dd148-236">UPD_ASSOC</span></span>  <br/> |<span data-ttu-id="dd148-237">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-237">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-238">UPD_MOV</span><span class="sxs-lookup"><span data-stu-id="dd148-238">UPD_MOV</span></span>  <br/> |<span data-ttu-id="dd148-239">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-239">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-240">UPD_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-240">UPD_OK</span></span>  <br/> |<span data-ttu-id="dd148-241">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-241">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-242">UPD_MOVED</span><span class="sxs-lookup"><span data-stu-id="dd148-242">UPD_MOVED</span></span>  <br/> |<span data-ttu-id="dd148-243">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-243">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-244">UPD_UPDATE</span><span class="sxs-lookup"><span data-stu-id="dd148-244">UPD_UPDATE</span></span>  <br/> |<span data-ttu-id="dd148-245">0x00040000</span><span class="sxs-lookup"><span data-stu-id="dd148-245">0x00040000</span></span>  <br/> |
|<span data-ttu-id="dd148-246">UPD_COMMIT</span><span class="sxs-lookup"><span data-stu-id="dd148-246">UPD_COMMIT</span></span>  <br/> |<span data-ttu-id="dd148-247">0x00080000</span><span class="sxs-lookup"><span data-stu-id="dd148-247">0x00080000</span></span>  <br/> |
|<span data-ttu-id="dd148-248">UPF_NEW</span><span class="sxs-lookup"><span data-stu-id="dd148-248">UPF_NEW</span></span>  <br/> |<span data-ttu-id="dd148-249">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-249">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-250">UPF_MOD_PARENT</span><span class="sxs-lookup"><span data-stu-id="dd148-250">UPF_MOD_PARENT</span></span>  <br/> |<span data-ttu-id="dd148-251">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-251">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-252">UPF_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="dd148-252">UPF_MOD_PROPS</span></span>  <br/> |<span data-ttu-id="dd148-253">0x00000004</span><span class="sxs-lookup"><span data-stu-id="dd148-253">0x00000004</span></span>  <br/> |
|<span data-ttu-id="dd148-254">UPF_DEL</span><span class="sxs-lookup"><span data-stu-id="dd148-254">UPF_DEL</span></span>  <br/> |<span data-ttu-id="dd148-255">0x00000008</span><span class="sxs-lookup"><span data-stu-id="dd148-255">0x00000008</span></span>  <br/> |
|<span data-ttu-id="dd148-256">UPF_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-256">UPF_OK</span></span>  <br/> |<span data-ttu-id="dd148-257">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-257">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-258">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-258">UPH_OK</span></span>  <br/> |<span data-ttu-id="dd148-259">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-259">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-260">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="dd148-260">UPM_ASSOC</span></span>  <br/> |<span data-ttu-id="dd148-261">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-261">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-262">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="dd148-262">UPM_NEW</span></span>  <br/> |<span data-ttu-id="dd148-263">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-263">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-264">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="dd148-264">UPM_MOV</span></span>  <br/> |<span data-ttu-id="dd148-265">0x00000004</span><span class="sxs-lookup"><span data-stu-id="dd148-265">0x00000004</span></span>  <br/> |
|<span data-ttu-id="dd148-266">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="dd148-266">UPM_MOD_PROPS</span></span>  <br/> |<span data-ttu-id="dd148-267">0x00000008</span><span class="sxs-lookup"><span data-stu-id="dd148-267">0x00000008</span></span>  <br/> |
|<span data-ttu-id="dd148-268">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="dd148-268">UPM_HEADER</span></span>  <br/> |<span data-ttu-id="dd148-269">0x00000010</span><span class="sxs-lookup"><span data-stu-id="dd148-269">0x00000010</span></span>  <br/> |
|<span data-ttu-id="dd148-270">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-270">UPM_OK</span></span>  <br/> |<span data-ttu-id="dd148-271">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-271">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-272">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="dd148-272">UPM_MOVED</span></span>  <br/> |<span data-ttu-id="dd148-273">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-273">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-274">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="dd148-274">UPM_COMMIT</span></span>  <br/> |<span data-ttu-id="dd148-275">0x00040000</span><span class="sxs-lookup"><span data-stu-id="dd148-275">0x00040000</span></span>  <br/> |
|<span data-ttu-id="dd148-276">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="dd148-276">UPM_DELETE</span></span>  <br/> |<span data-ttu-id="dd148-277">0x00080000</span><span class="sxs-lookup"><span data-stu-id="dd148-277">0x00080000</span></span>  <br/> |
|<span data-ttu-id="dd148-278">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="dd148-278">UPM_SAVE</span></span>  <br/> |<span data-ttu-id="dd148-279">0x00100000</span><span class="sxs-lookup"><span data-stu-id="dd148-279">0x00100000</span></span>  <br/> |
|<span data-ttu-id="dd148-280">UPR_ASSOC</span><span class="sxs-lookup"><span data-stu-id="dd148-280">UPR_ASSOC</span></span>  <br/> |<span data-ttu-id="dd148-281">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-281">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-282">UPR_READ</span><span class="sxs-lookup"><span data-stu-id="dd148-282">UPR_READ</span></span>  <br/> |<span data-ttu-id="dd148-283">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-283">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-284">UPR_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-284">UPR_OK</span></span>  <br/> |<span data-ttu-id="dd148-285">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-285">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-286">UPR_COMMIT</span><span class="sxs-lookup"><span data-stu-id="dd148-286">UPR_COMMIT</span></span>  <br/> |<span data-ttu-id="dd148-287">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-287">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-288">UPS_UPLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="dd148-288">UPS_UPLOAD_ONLY</span></span>  <br/> |<span data-ttu-id="dd148-289">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-289">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-290">UPS_DNLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="dd148-290">UPS_DNLOAD_ONLY</span></span>  <br/> |<span data-ttu-id="dd148-291">0x00000002</span><span class="sxs-lookup"><span data-stu-id="dd148-291">0x00000002</span></span>  <br/> |
|<span data-ttu-id="dd148-292">UPS_ONE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="dd148-292">UPS_ONE_FOLDER</span></span>  <br/> |<span data-ttu-id="dd148-293">0x00000004</span><span class="sxs-lookup"><span data-stu-id="dd148-293">0x00000004</span></span>  <br/> |
|<span data-ttu-id="dd148-294">UPS_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="dd148-294">UPS_THESE_FOLDERS</span></span>  <br/> |<span data-ttu-id="dd148-295">0x00000080</span><span class="sxs-lookup"><span data-stu-id="dd148-295">0x00000080</span></span>  <br/> |
|<span data-ttu-id="dd148-296">UPS_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-296">UPS_OK</span></span>  <br/> |<span data-ttu-id="dd148-297">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-297">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-298">UPT_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-298">UPT_OK</span></span>  <br/> |<span data-ttu-id="dd148-299">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-299">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-300">UPT_PUBLIC</span><span class="sxs-lookup"><span data-stu-id="dd148-300">UPT_PUBLIC</span></span>  <br/> |<span data-ttu-id="dd148-301">0x00000001</span><span class="sxs-lookup"><span data-stu-id="dd148-301">0x00000001</span></span>  <br/> |
|<span data-ttu-id="dd148-302">UPV_ERROR</span><span class="sxs-lookup"><span data-stu-id="dd148-302">UPV_ERROR</span></span>  <br/> |<span data-ttu-id="dd148-303">0x00010000</span><span class="sxs-lookup"><span data-stu-id="dd148-303">0x00010000</span></span>  <br/> |
|<span data-ttu-id="dd148-304">UPV_DIRTY</span><span class="sxs-lookup"><span data-stu-id="dd148-304">UPV_DIRTY</span></span>  <br/> |<span data-ttu-id="dd148-305">0x00020000</span><span class="sxs-lookup"><span data-stu-id="dd148-305">0x00020000</span></span>  <br/> |
|<span data-ttu-id="dd148-306">UPV_COMMIT</span><span class="sxs-lookup"><span data-stu-id="dd148-306">UPV_COMMIT</span></span>  <br/> |<span data-ttu-id="dd148-307">0x00040000</span><span class="sxs-lookup"><span data-stu-id="dd148-307">0x00040000</span></span>  <br/> |
   
### <a name="interface-declarations"></a><span data-ttu-id="dd148-308">接口声明</span><span class="sxs-lookup"><span data-stu-id="dd148-308">Interface declarations</span></span>

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportHierarchyChanges,PXIHC);
```

```cpp
DECLARE_MAPI_INTERFACE_PTR(IExchangeImportContentsChanges,PXICC);
```

### <a name="interface-identifiers"></a><span data-ttu-id="dd148-309">界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-309">Interface identifiers</span></span>

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

<span data-ttu-id="dd148-310">使用与[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、 [IMAPISession::OpenEntry](imapisession-openentry.md)或[IMsgStore::OpenEntry](imsgstore-openentry.md)两个以下接口标识符打开，并分别忽略 folder 对象和 message 对象，任何提供程序检查。</span><span class="sxs-lookup"><span data-stu-id="dd148-310">Use the two following interface identifiers with [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), or [IMsgStore::OpenEntry](imsgstore-openentry.md) to open and ignore any provider check on a folder object and a message object, respectively.</span></span> 
  
```cpp
//{57D333A0-F589-4b23-A3F9-85F82FEC153C}
DEFINE_GUID (IID_IMAPIFolderNoProvChk, 0x57D333A0, 0xF589, 0x4b23, 0xA3, 0xF9, 0x85, 0xF8, 0x2F, 0xEC, 0x15, 0x3C)
```

```cpp
//{C3505457-7B2E-4c3b-A8D6-6DD949BB97A1}
DEFINE_GUID (IID_IMessageNoProvChk, 0xC3505457, 0x7B2E, 0x4c3b, 0xA8, 0xD6, 0x6D, 0xD9, 0x49, 0xBB, 0x97, 0xA1)
```

## <a name="mapi-store"></a><span data-ttu-id="dd148-311">MAPI 存储区</span><span class="sxs-lookup"><span data-stu-id="dd148-311">MAPI store</span></span>

<span data-ttu-id="dd148-312">本节包含的常量定义和界面标识符由 Api 该接口与 MAPI 存储。</span><span class="sxs-lookup"><span data-stu-id="dd148-312">This section contains constant definitions and interface identifiers used by APIs that interface with a MAPI store.</span></span>
  
### <a name="constants"></a><span data-ttu-id="dd148-313">常量</span><span class="sxs-lookup"><span data-stu-id="dd148-313">Constants</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="dd148-314">fnevIndexing</span><span class="sxs-lookup"><span data-stu-id="dd148-314">fnevIndexing</span></span>  <br/> |<span data-ttu-id="dd148-315">（满足） 0X00010000）</span><span class="sxs-lookup"><span data-stu-id="dd148-315">((ULONG) 0x00010000)</span></span>  <br/> |<span data-ttu-id="dd148-316">存储提供程序可以指定**fnevIndexing**中的**[通知](notification.md)** 结构**ulEventType**成员，才能通知索引器对象是供索引。</span><span class="sxs-lookup"><span data-stu-id="dd148-316">A store provider can specify **fnevIndexing** in the **ulEventType** member of the **[NOTIFICATION](notification.md)** structure to notify the indexer that an object is ready for indexing.</span></span> <span data-ttu-id="dd148-317">**通知**结构的**信息**成员包含**[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="dd148-317">The **info** member of the **NOTIFICATION** structure contains an **[EXTENDED_NOTIFICATION](extended_notification.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="dd148-318">FS_NONE</span><span class="sxs-lookup"><span data-stu-id="dd148-318">FS_NONE</span></span>  <br/> |<span data-ttu-id="dd148-319">0x00</span><span class="sxs-lookup"><span data-stu-id="dd148-319">0x00</span></span>  <br/> |<span data-ttu-id="dd148-320">客户端可以对返回的位掩码调用**[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** 并检查。</span><span class="sxs-lookup"><span data-stu-id="dd148-320">A client can call **[IFolderSupport::GetSupportMask](ifoldersupport-getsupportmask.md)** and check for the returned bitmask.</span></span> <span data-ttu-id="dd148-321">**FS_NONE**指示该文件夹不支持共享。</span><span class="sxs-lookup"><span data-stu-id="dd148-321">**FS_NONE** indicates that the folder does not support sharing.</span></span>  <br/> |
|<span data-ttu-id="dd148-322">FS_SUPPORTS_SHARING</span><span class="sxs-lookup"><span data-stu-id="dd148-322">FS_SUPPORTS_SHARING</span></span>  <br/> |<span data-ttu-id="dd148-323">0x01</span><span class="sxs-lookup"><span data-stu-id="dd148-323">0x01</span></span>  <br/> |<span data-ttu-id="dd148-324">客户端可以对返回的位掩码调用**IFolderSupport::GetSupportMask**并检查。</span><span class="sxs-lookup"><span data-stu-id="dd148-324">A client can call **IFolderSupport::GetSupportMask** and check for the returned bitmask.</span></span> <span data-ttu-id="dd148-325">**FS_SUPPORTS_SHARING**指示文件夹支持共享。</span><span class="sxs-lookup"><span data-stu-id="dd148-325">**FS_SUPPORTS_SHARING** indicates that the folder supports sharing.</span></span>  <br/> |
|<span data-ttu-id="dd148-326">INDEXING_SEARCH_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd148-326">INDEXING_SEARCH_OWNER</span></span>  <br/> |<span data-ttu-id="dd148-327">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="dd148-327">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="dd148-328">标识向索引器对象是供索引推送通知的进程。</span><span class="sxs-lookup"><span data-stu-id="dd148-328">Identifies the process that is pushing a notification to an indexer that an object is ready for indexing.</span></span>  <br/> |
|<span data-ttu-id="dd148-329">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="dd148-329">MNID_ID</span></span>  <br/> |<span data-ttu-id="dd148-330">Microsoft Windows 软件开发工具包 (SDK) 标头文件 mapidefs.h 中定义</span><span class="sxs-lookup"><span data-stu-id="dd148-330">As defined in the Microsoft Windows Software Development Kit (SDK) header file mapidefs.h</span></span>  <br/> |<span data-ttu-id="dd148-331">一个**[MAPINAMEID](mapinameid.md)** 结构的**ulKind**字段的值。</span><span class="sxs-lookup"><span data-stu-id="dd148-331">A value for the **ulKind** field of the **[MAPINAMEID](mapinameid.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="dd148-332">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="dd148-332">MNID_STRING</span></span>  <br/> |<span data-ttu-id="dd148-333">Microsoft Windows 软件开发工具包 (SDK) 标头文件 mapidefs.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="dd148-333">As defined in the Microsoft Windows Software Development Kit (SDK) header file mapidefs.h.</span></span>  <br/> |<span data-ttu-id="dd148-334">一个**[MAPINAMEID](mapinameid.md)** 结构的**ulKind**字段的值。</span><span class="sxs-lookup"><span data-stu-id="dd148-334">A value for the **ulKind** field of the **[MAPINAMEID](mapinameid.md)** structure.</span></span>  <br/> |
|<span data-ttu-id="dd148-335">MSCAP_RES_ANNOTATION</span><span class="sxs-lookup"><span data-stu-id="dd148-335">MSCAP_RES_ANNOTATION</span></span>  <br/> |<span data-ttu-id="dd148-336">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="dd148-336">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="dd148-337">如果客户端指定**MSCAP_SEL_RESTRICTION** *mscapSelector* **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)**， **GetCapabilities**可以返回此值，如果存储忽略限制中的参数无效。</span><span class="sxs-lookup"><span data-stu-id="dd148-337">If a client specifies **MSCAP_SEL_RESTRICTION** in  *mscapSelector*  for **[IMSCapabilities::GetCapabilities](imscapabilities-getcapabilities.md)**, **GetCapabilities** can return this value if the store ignores invalid parameters in a restriction.</span></span>  <br/> |
|<span data-ttu-id="dd148-338">MSCAP_SECURE_FOLDER_HOMEPAGES</span><span class="sxs-lookup"><span data-stu-id="dd148-338">MSCAP_SECURE_FOLDER_HOMEPAGES</span></span>  <br/> |<span data-ttu-id="dd148-339">（满足） 0X00000020）</span><span class="sxs-lookup"><span data-stu-id="dd148-339">((ULONG) 0x00000020)</span></span>  <br/> |<span data-ttu-id="dd148-340">如果客户端指定**MSCAP_SEL_FOLDER** *mscapSelector* **IMSCapabilities::GetCapabilities**， **GetCapabilities**可以返回此值，如果存储是支持文件夹主页的非默认存储区。</span><span class="sxs-lookup"><span data-stu-id="dd148-340">If a client specifies **MSCAP_SEL_FOLDER** in  *mscapSelector*  for **IMSCapabilities::GetCapabilities**, **GetCapabilities** can return this value if the store is a non-default store that supports folder home pages.</span></span>  <br/> |
|<span data-ttu-id="dd148-341">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-341">STORE_PUSHER_OK</span></span>  <br/> |<span data-ttu-id="dd148-342">（满足） 0X00800000）</span><span class="sxs-lookup"><span data-stu-id="dd148-342">((ULONG) 0x00800000)</span></span>  <br/> |<span data-ttu-id="dd148-343">客户端可以获取**[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 来确定邮件存储的特征的属性。</span><span class="sxs-lookup"><span data-stu-id="dd148-343">A client can get the property **[PR_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** to determine the characteristic of a message store.</span></span> <span data-ttu-id="dd148-344">如果存储提供程序中的位掩码，是指 MAPI 协议处理程序将不存储进行爬网设置**STORE_PUSHER_OK**标志以及存储负责通过通知的任何更改推送到索引器已编制索引的邮件。</span><span class="sxs-lookup"><span data-stu-id="dd148-344">If the store provider sets the **STORE_PUSHER_OK** flag in the bitmask, that means the MAPI Protocol Handler will not crawl the store, and the store is responsible to push any changes through notifications to the indexer to have messages indexed.</span></span>  <br/> |
   
### <a name="definitions-for-namespaces"></a><span data-ttu-id="dd148-345">定义命名空间</span><span class="sxs-lookup"><span data-stu-id="dd148-345">Definitions for namespaces</span></span>

<span data-ttu-id="dd148-346">以下全局唯一标识符 (Guid) 表示命名属性的命名的空间。</span><span class="sxs-lookup"><span data-stu-id="dd148-346">The following globally unique identifiers (GUIDs) represent the namespaces of named properties.</span></span> <span data-ttu-id="dd148-347">他们编制索引的 MAPI 协议处理程序 (PH) 中，并以只读方式记录。</span><span class="sxs-lookup"><span data-stu-id="dd148-347">They are indexed by the MAPI Protocol Handler (PH), and are documented as read-only.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dd148-348">不应使用的命名的属性创建或修改的项目。</span><span class="sxs-lookup"><span data-stu-id="dd148-348">The named properties should not be used to create or modify items.</span></span> 
  
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

#### <a name="mnidid-properties"></a><span data-ttu-id="dd148-349">MNID_ID 属性</span><span class="sxs-lookup"><span data-stu-id="dd148-349">MNID_ID Properties</span></span>
  
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

#### <a name="mnidstring-properties"></a><span data-ttu-id="dd148-350">MNID_STRING 属性</span><span class="sxs-lookup"><span data-stu-id="dd148-350">MNID_STRING Properties</span></span>
  
```cpp
// In PS_PUBLIC_STRINGS 
"Keywords"
```

```cpp
// In PS_INTERNET_HEADERS
"return-path"
```

### <a name="interface-identifiers"></a><span data-ttu-id="dd148-351">界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-351">Interface identifiers</span></span>

```cpp
//{00375ac3-ecaf-4ef8-a527-34f452fa9c67}
DEFINE_GUID(IID_IFolderSupport, 0x00375ac3, 0xecaf, 0x4ef8, 0xa5, 0x27, 0x34, 0xf4, 0x52, 0xfa, 0x9c, 0x67);

```

```cpp
//{29F3AB10-554d-11d0-a97c-00a0c911f50a}
#define DEFINE_PRXGUID(_name, _l) DEFINE_GUID(_name, (0x29f3ab10 + _l), 0x554d, 0x11d0, 0xa9, 0x7c, 0x00, 0xa0, 0xc9, 0x11, 0xf5, 0x0a) 
DEFINE_PRXGUID(IID_IProxyStoreObject, 0x00000000L);
```

<span data-ttu-id="dd148-352">使用`DEFINE_OLEGUID`其值与关联的以下 GUID 符号名称 Windows SDK 标头文件 guiddef.h 中定义的宏。</span><span class="sxs-lookup"><span data-stu-id="dd148-352">Use the  `DEFINE_OLEGUID` macro defined in the Windows SDK header file guiddef.h to associate the following GUID symbolic name with its value.</span></span> 
  
```cpp
//{00020393-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_IMSCapabilities, 0x00020393, 0, 0)

```

## <a name="mapi-address-book-constants"></a><span data-ttu-id="dd148-353">MAPI 通讯簿常量</span><span class="sxs-lookup"><span data-stu-id="dd148-353">MAPI Address Book constants</span></span>

<span data-ttu-id="dd148-354">此部分包含常量定义的 MAPI 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="dd148-354">This section contains constant definitions for the MAPI Address Book.</span></span>
  
### <a name="constants"></a><span data-ttu-id="dd148-355">常量</span><span class="sxs-lookup"><span data-stu-id="dd148-355">Constants</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="dd148-356">CONTAB_ROOT</span><span class="sxs-lookup"><span data-stu-id="dd148-356">CONTAB_ROOT</span></span>  <br/> |<span data-ttu-id="dd148-357">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="dd148-357">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="dd148-358">MAPI 通讯簿对象的的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd148-358">The root folder for a MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="dd148-359">CONTAB_SUBROOT</span><span class="sxs-lookup"><span data-stu-id="dd148-359">CONTAB_SUBROOT</span></span>  <br/> |<span data-ttu-id="dd148-360">（满足） 0X00000002:UC）</span><span class="sxs-lookup"><span data-stu-id="dd148-360">((ULONG) 0x00000002)</span></span>  <br/> |<span data-ttu-id="dd148-361">MAPI 通讯簿对象的根文件夹中包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd148-361">A subfolder contained within the root folder of the MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="dd148-362">CONTAB_CONTAINER</span><span class="sxs-lookup"><span data-stu-id="dd148-362">CONTAB_CONTAINER</span></span>  <br/> |<span data-ttu-id="dd148-363">（满足） 0X00000003）</span><span class="sxs-lookup"><span data-stu-id="dd148-363">((ULONG) 0x00000003)</span></span>  <br/> |<span data-ttu-id="dd148-364">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="dd148-364">An address book container object.</span></span>  <br/> |
|<span data-ttu-id="dd148-365">CONTAB_USER</span><span class="sxs-lookup"><span data-stu-id="dd148-365">CONTAB_USER</span></span>  <br/> |<span data-ttu-id="dd148-366">（满足） 0X00000004）</span><span class="sxs-lookup"><span data-stu-id="dd148-366">((ULONG) 0x00000004)</span></span>  <br/> |<span data-ttu-id="dd148-367">消息的用户对象。</span><span class="sxs-lookup"><span data-stu-id="dd148-367">A messaging user object.</span></span>  <br/> |
|<span data-ttu-id="dd148-368">CONTAB_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="dd148-368">CONTAB_DISTLIST</span></span>  <br/> |<span data-ttu-id="dd148-369">（满足） 0X00000005）</span><span class="sxs-lookup"><span data-stu-id="dd148-369">((ULONG) 0x00000005)</span></span>  <br/> |<span data-ttu-id="dd148-370">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="dd148-370">A distribution list object.</span></span>  <br/> |
   
## <a name="additional-mapi-constants"></a><span data-ttu-id="dd148-371">其他 MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="dd148-371">Additional MAPI constants</span></span>

<span data-ttu-id="dd148-372">此部分包含包括错误代码和界面标识符的以前没有公开并记录了 MAPI Api 使用的常量定义。</span><span class="sxs-lookup"><span data-stu-id="dd148-372">This section contains constant definitions including error codes, and interface identifiers used by MAPI APIs that were not previously exposed and documented.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="dd148-373">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="dd148-373">DIALOG_MODAL</span></span>  <br/> |<span data-ttu-id="dd148-374">（满足） 0X00000001）</span><span class="sxs-lookup"><span data-stu-id="dd148-374">((ULONG) 0x00000001)</span></span>  <br/> |<span data-ttu-id="dd148-375">当客户端调用[IAddrBook::Details](iaddrbook-details.md)方法时，则客户端必须在_ulFlags_参数来显示模式对话框显示有关特定通讯簿条目的详细信息设置**DIALOG_MODAL**标志。</span><span class="sxs-lookup"><span data-stu-id="dd148-375">When a client calls the [IAddrBook::Details](iaddrbook-details.md) method, the client must set the **DIALOG_MODAL** flag in the  _ulFlags_ parameter to display the modal dialog box showing the details about a particular address book entry.</span></span> <span data-ttu-id="dd148-376">此常量 mapidefs.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="dd148-376">This constant is defined in mapidefs.h.</span></span>  <br/> |
|<span data-ttu-id="dd148-377">ITEMPROC_FORCE</span><span class="sxs-lookup"><span data-stu-id="dd148-377">ITEMPROC_FORCE</span></span>  <br/> |<span data-ttu-id="dd148-378">0x00000800</span><span class="sxs-lookup"><span data-stu-id="dd148-378">0x00000800</span></span>  <br/> |<span data-ttu-id="dd148-379">在 Outlook 2007 中，换行的 PST 存储有规则垃圾邮件筛选在和处理新邮件通知新消息的 MAPI 客户端之前。</span><span class="sxs-lookup"><span data-stu-id="dd148-379">In Outlook 2007, wrapped PST stores have rules and spam filtering processed on new messages before MAPI clients are notified of the new messages.</span></span> <span data-ttu-id="dd148-380">提供程序或使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法在 PST 存储中创建一个新的邮件客户端应[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以指示到 PST 的_ulFlags_参数中设置**ITEMPROC_FORCE**标志存储邮件符合条件的规则处理之前存储通知新消息的到达任何侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="dd148-380">A provider or client using the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method to create a new message in PST stores should set the **ITEMPROC_FORCE** flag in the  _ulFlags_ parameter of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to indicate to the PST store that the message is eligible for rules processing before the store notifies any listening client of the arrival of the new message.</span></span> <span data-ttu-id="dd148-381">请注意，仅处理此类规则适用于新邮件不是 Microsoft Exchange Server，服务器上创建，因为 Exchange 服务器处理的服务器上的邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="dd148-381">Note that such rules processing only applies to new messages created on a server that is not a Microsoft Exchange Server, because Exchange Server processes rules for messages on the server.</span></span> <span data-ttu-id="dd148-382">因此提供程序或创建邮件客户端必须通过此标志与**NON_EMS_XP_SAVE**，这表明服务器不是 Exchange server 结合使用。</span><span class="sxs-lookup"><span data-stu-id="dd148-382">Hence the provider or client creating the message must pass this flag in combination with **NON_EMS_XP_SAVE**, which indicates the server is not an Exchange server.</span></span>  <br/> |
| <span data-ttu-id="dd148-383">MAPI_BG_SESSION</span><span class="sxs-lookup"><span data-stu-id="dd148-383">MAPI_BG_SESSION</span></span>  <br/> |<span data-ttu-id="dd148-384">0x00200000</span><span class="sxs-lookup"><span data-stu-id="dd148-384">0x00200000</span></span>  <br/> |<span data-ttu-id="dd148-385">客户端可以调用[MAPILogonEx](mapilogonex.md)函数中，登录到会话，并执行任何操作在后台_flFlags_参数中设置**MAPI_BG_SESSION**标志。</span><span class="sxs-lookup"><span data-stu-id="dd148-385">A client can call the [MAPILogonEx](mapilogonex.md) function, setting the **MAPI_BG_SESSION** flag in the  _flFlags_ parameter to log on to a session and carry out any operations in the background.</span></span> <span data-ttu-id="dd148-386">一般来说，如果打算执行后台线程上或在单独的进程中不到前台线程引人注目的方式处理客户端，它应与**MAPI_BG_SESSION**标志调用[MAPILogonEx](mapilogonex.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd148-386">In general, if a client intends to do processing on a background thread or in a separate process in a manner that is unobtrusive to the foreground thread, it should call [MAPILogonEx](mapilogonex.md) with the **MAPI_BG_SESSION** flag.</span></span> <span data-ttu-id="dd148-387">使用此示例是一个客户端应用程序，如索引引擎，打开背景类型访问个人文件夹文件 (PST)。</span><span class="sxs-lookup"><span data-stu-id="dd148-387">An example where this is used is a client application, such as an indexing engine, opening a Personal Folders File (PST) for background type access.</span></span>  <br/> |
|<span data-ttu-id="dd148-388">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="dd148-388">MAPI_CACHE_ONLY</span></span>  <br/> |<span data-ttu-id="dd148-389">0x00004000</span><span class="sxs-lookup"><span data-stu-id="dd148-389">0x00004000</span></span>  <br/> |<span data-ttu-id="dd148-390">客户端可以调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)方法，将**MAPI_CACHE_ONLY**标志设置_ulFlags_参数可打开的通讯簿条目并可访问该随后仅从缓存中。</span><span class="sxs-lookup"><span data-stu-id="dd148-390">A client can call the [IAddrBook::OpenEntry](iaddrbook-openentry.md) method, setting the **MAPI_CACHE_ONLY** flag in the  _ulFlags_ parameter to open an address book entry and to access it subsequently only from the cache.</span></span> <span data-ttu-id="dd148-391">使用此示例是想要在缓存 Exchange 模式下打开全局地址列表和从缓存中访问该通讯簿中的条目，而不创建客户端和服务器之间的通信客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="dd148-391">An example where this is used is a client application that wants to open the Global Address List in Cached Exchange mode and access an entry in that Address Book from the cache without creating traffic between the client and the server.</span></span>  <br/> |
|<span data-ttu-id="dd148-392">MAPI_DIALOG_MODELESS</span><span class="sxs-lookup"><span data-stu-id="dd148-392">MAPI_DIALOG_MODELESS</span></span>  <br/> |<span data-ttu-id="dd148-393">0x0000000C</span><span class="sxs-lookup"><span data-stu-id="dd148-393">0x0000000C</span></span>  <br/> |<span data-ttu-id="dd148-394">此值传递给使用_ulFlags_参数指定将无模式对话框显示默认邮件应用程序中的简单 MAPI MAPISendMail 函数。</span><span class="sxs-lookup"><span data-stu-id="dd148-394">This value can be passed to the Simple MAPI MAPISendMail function in the  _ulFlags_ parameter to specify that a modeless dialog box is displayed by the default mail application.</span></span> <span data-ttu-id="dd148-395">如果设置此标志和 MAPI_DIALOG (0x00000008) 都不被不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="dd148-395">If neither this flag nor MAPI_DIALOG (0x00000008) is set, no dialog box is displayed.</span></span>  <br/> |
|<span data-ttu-id="dd148-396">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="dd148-396">MAPI_NO_CACHE</span></span>  <br/> |<span data-ttu-id="dd148-397">0x00000200</span><span class="sxs-lookup"><span data-stu-id="dd148-397">0x00000200</span></span>  <br/> |<span data-ttu-id="dd148-398">如果是在缓存 Exchange 模式下的 Microsoft Office Outlook 和存储区中缓存模式已打开，客户端或服务提供程序可以呼叫[IMsgStore::OpenEntry](imsgstore-openentry.md)， _ulFlags_参数打开一个项目中设置**MAPI_NO_CACHE**标志或远程存储的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd148-398">If Microsoft Office Outlook is in Cached Exchange Mode and a store has been opened in cached mode, a client or service provider can call [IMsgStore::OpenEntry](imsgstore-openentry.md), setting the **MAPI_NO_CACHE** flag in the  _ulFlags_ parameter to open an item or a folder on the remote store.</span></span> <span data-ttu-id="dd148-399">请注意，是否您使用**MDB_ONLINE**标志远程服务器上打开的消息存储，不需要使用**MAPI_NO_CACHE**标志。</span><span class="sxs-lookup"><span data-stu-id="dd148-399">Note that if you open the message store with the **MDB_ONLINE** flag on the remote server, you do not have to use the **MAPI_NO_CACHE** flag.</span></span>  <br/> |
|<span data-ttu-id="dd148-400">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dd148-400">MAPI_UNICODE</span></span>  <br/> |<span data-ttu-id="dd148-401">0x80000000</span><span class="sxs-lookup"><span data-stu-id="dd148-401">0x80000000</span></span>  <br/> |<span data-ttu-id="dd148-402">客户端或服务提供程序可以调用[OpenIMsgOnIStg](openimsgonistg.md)函数， _ulFlags_参数创建 Unicode.msg 文件中设置**MAPI_UNICODE**标志。</span><span class="sxs-lookup"><span data-stu-id="dd148-402">A client or service provider can call the [OpenIMsgOnIStg](openimsgonistg.md) function, setting the **MAPI_UNICODE** flag in the  _ulFlags_ parameter to create Unicode .msg files.</span></span> <span data-ttu-id="dd148-403">产生的[IMessage: IMAPIProp](imessageimapiprop.md)文件中其[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)显示**STORE_UNICODE_OK**且支持 Unicode 属性。</span><span class="sxs-lookup"><span data-stu-id="dd148-403">The resulting [IMessage : IMAPIProp](imessageimapiprop.md) file shows **STORE_UNICODE_OK** in its [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md) and supports Unicode properties.</span></span> <span data-ttu-id="dd148-404">此常量 mapidefs.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="dd148-404">This constant is defined in mapidefs.h.</span></span>  <br/> |
|<span data-ttu-id="dd148-405">MDB_ONLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-405">MDB_ONLINE</span></span>  <br/> |<span data-ttu-id="dd148-406">0x00000100</span><span class="sxs-lookup"><span data-stu-id="dd148-406">0x00000100</span></span>  <br/> |<span data-ttu-id="dd148-407">如果 Outlook 为缓存 Exchange 模式下，客户端或服务提供程序可以调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法， _ulFlags_参数覆盖本地消息存储库的连接并打开中设置**MDB_ONLINE**标志远程服务器上存储。</span><span class="sxs-lookup"><span data-stu-id="dd148-407">If Outlook is in Cached Exchange Mode, a client or service provider can call the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method, setting the **MDB_ONLINE** flag in the  _ulFlags_ parameter to override the connection to the local message store and open the store on the remote server.</span></span> <span data-ttu-id="dd148-408">请注意，您不能打开 Exchange 存储在缓存模式和非缓存模式下在同一 MAPI 会话中的同一时间。</span><span class="sxs-lookup"><span data-stu-id="dd148-408">Note that you cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="dd148-409">如果您已经打开的缓存的消息存储之前，必须也关闭存储打开与此标志，或打开新其中可以使用此标志打开 Exchange 存储的远程服务器上的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="dd148-409">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>  <br/> |
|<span data-ttu-id="dd148-410">NON_EMS_XP_SAVE</span><span class="sxs-lookup"><span data-stu-id="dd148-410">NON_EMS_XP_SAVE</span></span>  <br/> |<span data-ttu-id="dd148-411">0x00001000</span><span class="sxs-lookup"><span data-stu-id="dd148-411">0x00001000</span></span>  <br/> |<span data-ttu-id="dd148-412">客户端可以调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，将**NON_EMS_XP_SAVE**标志设置_ulFlags_参数来指示邮件尚未传递从 Exchange 服务器中。</span><span class="sxs-lookup"><span data-stu-id="dd148-412">A client can call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method, setting the **NON_EMS_XP_SAVE** flag in the  _ulFlags_ parameter to indicate that the message has not been delivered from an Exchange server.</span></span> <span data-ttu-id="dd148-413">此标志应该用于结合使用_ulFlags_参数中的**ITEMPROC_FORCE**标志指示邮件是适合规则处理之前 PST PST 存储通知的到达任何侦听客户端消息。</span><span class="sxs-lookup"><span data-stu-id="dd148-413">This flag should be used in combination with the **ITEMPROC_FORCE** flag in the  _ulFlags_ parameter to indicate to a PST store that the message is eligible for rules processing before the PST store notifies any listening client of the arrival of the message.</span></span> <span data-ttu-id="dd148-414">此规则处理仅适用于在不是 Exchange 服务器 （在这种情况下 Exchange 服务器会已经处理邮件的规则） 的服务器创建与[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)的新邮件。</span><span class="sxs-lookup"><span data-stu-id="dd148-414">This rules processing only applies to new messages that are created with [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) on a server that is not an Exchange server (in which case the Exchange server would have already processed rules on the message).</span></span>  <br/> |
|<span data-ttu-id="dd148-415">SPAMFILTER_ONSAVE</span><span class="sxs-lookup"><span data-stu-id="dd148-415">SPAMFILTER_ONSAVE</span></span>  <br/> |<span data-ttu-id="dd148-416">0x00000080</span><span class="sxs-lookup"><span data-stu-id="dd148-416">0x00000080</span></span>  <br/> |<span data-ttu-id="dd148-417">客户端可以调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)，在要启用垃圾邮件筛选上一条消息，正在保存的_ulFlags_参数中设置**SPAMFILTER_ONSAVE**标志。</span><span class="sxs-lookup"><span data-stu-id="dd148-417">A client can call [IMAPIProp::SaveChanges](imapiprop-savechanges.md), setting the **SPAMFILTER_ONSAVE** flag in the  _ulFlags_ parameter to enable spam filtering on a message that is being saved.</span></span> <span data-ttu-id="dd148-418">只有当发件人的电子邮件地址类型为简单邮件传输协议 (SMTP)，并且将存储个人文件夹文件 (PST) 用于保存邮件的垃圾邮件筛选支持可用。</span><span class="sxs-lookup"><span data-stu-id="dd148-418">Spam filtering support is available only if the sender's email address type is Simple Mail Transfer Protocol (SMTP), and the message is being saved to a store for a Personal Folders file (PST).</span></span>  <br/> |
|<span data-ttu-id="dd148-419">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="dd148-419">STORE_ITEMPROC</span></span>  <br/> |<span data-ttu-id="dd148-420">0x00200000</span><span class="sxs-lookup"><span data-stu-id="dd148-420">0x00200000</span></span>  <br/> |<span data-ttu-id="dd148-421">如果换行 PST 存储[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)中设置此标志，则表示当新邮件到达存储，存储的规则，并且垃圾邮件筛选单独对邮件处理。</span><span class="sxs-lookup"><span data-stu-id="dd148-421">If this flag is set in the [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md) of a wrapped PST store, it indicates that when a new message arrives at the store, the store has rules and spam filtering processed on the message separately.</span></span> <span data-ttu-id="dd148-422">存储然后调用[IMAPISupport::Notify](imapisupport-notify.md)，设置**fnevNewMail**中作为参数，传递的[通知](notification.md)结构并将新消息的详细信息传递给侦听的客户端。</span><span class="sxs-lookup"><span data-stu-id="dd148-422">The store then calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and passing the details of the new message to a listening client.</span></span> <span data-ttu-id="dd148-423">随后，侦听客户端接收通知时，它不处理邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="dd148-423">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span>  <br/> |
|<span data-ttu-id="dd148-424">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="dd148-424">STORE_UNICODE_OK</span></span>  <br/> |<span data-ttu-id="dd148-425">0x00040000</span><span class="sxs-lookup"><span data-stu-id="dd148-425">0x00040000</span></span>  <br/> |<span data-ttu-id="dd148-426">如果此标志包括在[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)，它指示的存储支持 Unicode 存储。</span><span class="sxs-lookup"><span data-stu-id="dd148-426">If this flag is included in the [PidTagStoreSupportMask Canonical Property](pidtagstoresupportmask-canonical-property.md), it indicates that the store supports Unicode storage.</span></span> <span data-ttu-id="dd148-427">客户端可以查看此标志以确定是请求还是将 Unicode 信息保存到存储的状态。</span><span class="sxs-lookup"><span data-stu-id="dd148-427">A client can look for the presence of the flag to decide whether to request or to save Unicode information to the store.</span></span>  <br/> |
   
### <a name="definitions-for-archiving-items-in-a-folder"></a><span data-ttu-id="dd148-428">定义存档文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="dd148-428">Definitions for archiving items in a folder</span></span>

<span data-ttu-id="dd148-429">以下常量定义是用于设置[PidTagAgingGranularity 规范属性](pidtagaginggranularity-canonical-property.md)的值。</span><span class="sxs-lookup"><span data-stu-id="dd148-429">The following constant definitions are values used to set the [PidTagAgingGranularity Canonical Property](pidtagaginggranularity-canonical-property.md).</span></span>
  
```cpp
#define AG_MONTHS 0 
#define AG_WEEKS  1 
#define AG_DAYS   2 

```

### <a name="definitions-for-displaying-remote-objects"></a><span data-ttu-id="dd148-430">定义用于显示远程对象</span><span class="sxs-lookup"><span data-stu-id="dd148-430">Definitions for displaying remote objects</span></span>

<span data-ttu-id="dd148-431">以下常量和宏定义所显示远程对象。</span><span class="sxs-lookup"><span data-stu-id="dd148-431">The following constant and macro definitions are for displaying remote objects.</span></span> <span data-ttu-id="dd148-432">有关详细信息，请参阅[PidTagDisplayTypeEx 规范属性](pidtagdisplaytypeex-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="dd148-432">For more information, see the [PidTagDisplayTypeEx Canonical Property](pidtagdisplaytypeex-canonical-property.md).</span></span>
  
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

### <a name="definitions-for-exchange-address-book-and-message-store-error-codes"></a><span data-ttu-id="dd148-433">定义 Exchange 通讯簿和邮件存储错误代码</span><span class="sxs-lookup"><span data-stu-id="dd148-433">Definitions for Exchange address book and Message store error codes</span></span>

<span data-ttu-id="dd148-434">以下包含具有重新连接功能的 Exchange 通讯簿和邮件存储的错误代码定义。</span><span class="sxs-lookup"><span data-stu-id="dd148-434">The following contains error code definitions for the Exchange Address Book and Message Store, which have reconnection capability.</span></span> <span data-ttu-id="dd148-435">向已断开连接全局编录 (GC) 的最后一个呼叫可能会导致**MAPI_E_END_OF_SESSION**错误，需要重试。</span><span class="sxs-lookup"><span data-stu-id="dd148-435">The last call to a disconnected Global Catalog (GC) may result in the **MAPI_E_END_OF_SESSION** error, which would need to be retried.</span></span> 
  
<span data-ttu-id="dd148-436">Outlook 的 MAPI 支持重新连接到 GC 服务器没有特殊重新配置，但其他一些错误代码返回客户端。</span><span class="sxs-lookup"><span data-stu-id="dd148-436">Outlook's MAPI supports reconnection to a GC server without special reconfiguration, but some other error codes can be returned to the client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="dd148-437">MAPI_E_END_OF_SESSION</span><span class="sxs-lookup"><span data-stu-id="dd148-437">MAPI_E_END_OF_SESSION</span></span>  <br/> |<span data-ttu-id="dd148-438">0x80040200</span><span class="sxs-lookup"><span data-stu-id="dd148-438">0x80040200</span></span>  <br/> |<span data-ttu-id="dd148-439">返回时已断开连接。</span><span class="sxs-lookup"><span data-stu-id="dd148-439">Returned when a connection has been disconnected.</span></span>  <br/> |
|<span data-ttu-id="dd148-440">MAPI_E_RECONNECTED</span><span class="sxs-lookup"><span data-stu-id="dd148-440">MAPI_E_RECONNECTED</span></span>  <br/> |<span data-ttu-id="dd148-441">0x80040125</span><span class="sxs-lookup"><span data-stu-id="dd148-441">0x80040125</span></span>  <br/> |<span data-ttu-id="dd148-442">远程过程调用 (RPC) 连接令牌已过期时返回。</span><span class="sxs-lookup"><span data-stu-id="dd148-442">Returned when the Remote Procedure Call (RPC) connection token is out-of-date.</span></span> <span data-ttu-id="dd148-443">如果当前事务的令牌不同的连接的意味着它的令牌已重新连接，因此**MAPI_E_RECONNECTED**返回，并且可以是相同视为**MAPI_E_END_OF_SESSION**。</span><span class="sxs-lookup"><span data-stu-id="dd148-443">If the token of the current transaction is different from the token of the connection that means it has reconnected, so **MAPI_E_RECONNECTED** is returned and can be treated the same as **MAPI_E_END_OF_SESSION**.</span></span> <span data-ttu-id="dd148-444">应重试呼叫。</span><span class="sxs-lookup"><span data-stu-id="dd148-444">The call should be retried.</span></span>  <br/> |
|<span data-ttu-id="dd148-445">MAPI_E_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="dd148-445">MAPI_E_OFFLINE</span></span>  <br/> |<span data-ttu-id="dd148-446">0x80040126</span><span class="sxs-lookup"><span data-stu-id="dd148-446">0x80040126</span></span>  <br/> |<span data-ttu-id="dd148-447">返回当连接处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="dd148-447">Returned when the connection is offline.</span></span> <span data-ttu-id="dd148-448">通常，这意味着事物发生在环境中，例如服务器故障或丢失网络连接。</span><span class="sxs-lookup"><span data-stu-id="dd148-448">Typically this means that something has occurred in the environment, such as server failure or loss of network connectivity.</span></span> <span data-ttu-id="dd148-449">此错误是最有可能发生时使用缓存的模式配置文件和尝试绕过缓存与服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="dd148-449">This error is most likely to occur when using a cached mode profile and attempting to bypass the cache to communicate with the server.</span></span> <span data-ttu-id="dd148-450">如果缓存从不能够最初建立与服务器的连接，则它可能处于脱机状态**MAPI_E_OFFLINE**无法显示顺序。</span><span class="sxs-lookup"><span data-stu-id="dd148-450">If the cache was never able to initially establish a connection to the server, it may be in the offline state in which **MAPI_E_OFFLINE** could surface.</span></span>  <br/> |
   
<span data-ttu-id="dd148-451">都不上述两个错误将返回所有方案中，它们将可能出现应用。</span><span class="sxs-lookup"><span data-stu-id="dd148-451">Neither of the preceding two errors will be returned in all scenarios where they would likely appear to apply.</span></span> <span data-ttu-id="dd148-452">在大多数情况下， **MAPI\_E_NETWORK_ERROR**或将返回**MAPI_E_CALL_FAILED** 。</span><span class="sxs-lookup"><span data-stu-id="dd148-452">In most cases, **MAPI\_E_NETWORK_ERROR** or **MAPI_E_CALL_FAILED** will be returned.</span></span> <span data-ttu-id="dd148-453">都不会使用[Microsoft Exchange Server MAPI 客户端和协作数据对象 1.2.1 （英文）](http://support.microsoft.com/kb/171440)下载。</span><span class="sxs-lookup"><span data-stu-id="dd148-453">Neither will appear using the [Microsoft Exchange Server MAPI Client and Collaboration Data Objects 1.2.1](http://support.microsoft.com/kb/171440) download.</span></span> 
  
### <a name="definitions-for-exchange-server-mailbox-cached-mode-quotas"></a><span data-ttu-id="dd148-454">Exchange Server 邮箱定义缓存模式配额</span><span class="sxs-lookup"><span data-stu-id="dd148-454">Definitions for Exchange Server Mailbox cached mode quotas</span></span>

<span data-ttu-id="dd148-455">以下常量定义使用 Microsoft Outlook 2010 和 Microsoft Outlook 2013 设置 Exchange 缓存等同于否则为仅与联机配置可用的 Exchange 邮箱配额的模式配置文件配额。</span><span class="sxs-lookup"><span data-stu-id="dd148-455">The following constant definitions are used by Microsoft Outlook 2010 and Microsoft Outlook 2013 to set the Exchange cached mode profile quotas that are equivalent to the Exchange mailbox quotas otherwise available only with an online profile.</span></span>
  
```cpp
#define PR_QUOTA_WARNING PROP_TAG( PT_LONG, 0x341A)
#define PR_QUOTA_SEND    PROP_TAG( PT_LONG, 0x341B)
#define PR_QUOTA_RECEIVE PROP_TAG( PT_LONG, 0x341C)
```

<span data-ttu-id="dd148-456">这些属性映射到其相对应的联机属性，并包含相同的值为千字节。</span><span class="sxs-lookup"><span data-stu-id="dd148-456">These properties map to their correspondent online properties and contain the same values in kilobytes.</span></span> <span data-ttu-id="dd148-457">PR_QUOTA_WARNING 映射到 PR_STORAGE_QUOTA_LIMIT，PR_QUOTA_SEND 到 PR_QUOTA_PROHIBIT_SEND_QUOTA，并为 PR_PROHIBIT_RECEIVE_QUOTA PR_QUOTA_RECEIVE。</span><span class="sxs-lookup"><span data-stu-id="dd148-457">PR_QUOTA_WARNING maps to PR_STORAGE_QUOTA_LIMIT, PR_QUOTA_SEND to PR_QUOTA_PROHIBIT_SEND_QUOTA, and PR_QUOTA_RECEIVE to PR_PROHIBIT_RECEIVE_QUOTA.</span></span>
  
### <a name="definitions-for-message-format"></a><span data-ttu-id="dd148-458">定义邮件格式</span><span class="sxs-lookup"><span data-stu-id="dd148-458">Definitions for message format</span></span>

<span data-ttu-id="dd148-459">以下常量定义是用于设置[PidTagMessageEditorFormat 规范属性](pidtagmessageeditorformat-canonical-property.md)的值。</span><span class="sxs-lookup"><span data-stu-id="dd148-459">The following constant definitions are values that are used to set the [PidTagMessageEditorFormat Canonical Property](pidtagmessageeditorformat-canonical-property.md).</span></span>
  
```cpp
#define EDITOR_FORMAT_DONTKNOW  ((ULONG) 0) 
#define EDITOR_FORMAT_PLAINTEXT ((ULONG) 1) 
#define EDITOR_FORMAT_HTML      ((ULONG) 2) 
#define EDITOR_FORMAT_RTF       ((ULONG) 3)
```

### <a name="definitions-for-using-rpc-over-http"></a><span data-ttu-id="dd148-460">使用 RPC over HTTP 的定义</span><span class="sxs-lookup"><span data-stu-id="dd148-460">Definitions for using RPC over HTTP</span></span>

<span data-ttu-id="dd148-461">请参阅用作标志将属性设置的常量定义的[PidTagRpcOverHttpFlags 规范属性](pidtagrpcoverhttpflags-canonical-property.md)主题。</span><span class="sxs-lookup"><span data-stu-id="dd148-461">See the [PidTagRpcOverHttpFlags Canonical Property](pidtagrpcoverhttpflags-canonical-property.md) topic for constant definitions used as flags to set the property.</span></span> 
  
<span data-ttu-id="dd148-462">请参阅用于将属性设置的常量定义的[PidTagRpcOverHttpProxyAuthScheme 规范属性](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)主题。</span><span class="sxs-lookup"><span data-stu-id="dd148-462">See the [PidTagRpcOverHttpProxyAuthScheme Canonical Property](pidtagrpcoverhttpproxyauthscheme-canonical-property.md) topic for constant definitions used to set the property.</span></span> 
  
### <a name="identifiers"></a><span data-ttu-id="dd148-463">标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-463">Identifiers</span></span>

<span data-ttu-id="dd148-464">使用`DEFINE_OLEGUID`Microsoft Windows 软件开发工具包 (SDK) 的标头文件 guiddef.h，将以下 GUID 符号名称相关联的值中定义的宏。</span><span class="sxs-lookup"><span data-stu-id="dd148-464">Use the  `DEFINE_OLEGUID` macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate the following GUID symbolic names with their values.</span></span> 
  
```cpp
//{0002038A-0000-0000-C000-000000000046}
#if !defined(INITGUID) || defined(USES_IID_IMessageRaw) 
DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0); 
#endif
```

<span data-ttu-id="dd148-465">下列标识符是通讯簿，它支持多个 Exchange ([MultiEx](using-multiple-exchange-accounts.md)) 邮箱中包含的[PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性的有效地关闭默认 Capone 配置文件一节指定[SetDefaultDir](iaddrbook-setdefaultdir.md)的容器。</span><span class="sxs-lookup"><span data-stu-id="dd148-465">The following Identifier is for the Capone Profile section of an Address Book, which in support of multiple Exchange ([MultiEx](using-multiple-exchange-accounts.md)) mailboxes contains a [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property that effectively turns off the default container specified by [SetDefaultDir](iaddrbook-setdefaultdir.md).</span></span>
  
```cpp
// {00020D0A-0000-0000-C000-000000000046}
DEFINE_OLEGUID(IID_CAPONE_PROF, 0x00020d0a, 0, 0);
```

### <a name="interface-identifiers"></a><span data-ttu-id="dd148-466">界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-466">Interface identifiers</span></span>

#### <a name="imapisync"></a><span data-ttu-id="dd148-467">IMAPISync</span><span class="sxs-lookup"><span data-stu-id="dd148-467">IMAPISync</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISync, 0x5024a385, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);

```

#### <a name="imapisyncprogresscallback"></a><span data-ttu-id="dd148-468">IMAPISyncProgressCallback</span><span class="sxs-lookup"><span data-stu-id="dd148-468">IMAPISyncProgressCallback</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISyncProgressCallback, 0x5024a386, 0x2d44, 0x486a,  0x81, 0xa8, 0x8f, 0xe, 0xcb, 0x60, 0x71, 0xdd);
```

#### <a name="iidicontabadmin"></a><span data-ttu-id="dd148-469">IID_IContabAdmin</span><span class="sxs-lookup"><span data-stu-id="dd148-469">IID_IContabAdmin</span></span>
  
```cpp
// {CC6A3BA9-E7F5-4769-887B-34E190817BFC}
DEFINE_GUID(IID_IContabAdmin, 0xcc6a3ba9, 0xe7f5, 0x4769, 0x88, 0x7b, 0x34, 0xe1, 0x90, 0x81, 0x7b, 0xfc);

```

#### <a name="iidimapisecuremessage"></a><span data-ttu-id="dd148-470">IID_IMAPISECUREMESSAGE</span><span class="sxs-lookup"><span data-stu-id="dd148-470">IID_IMAPISECUREMESSAGE</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPISecureMessage, 0x253cc320, 0xeab6, 0x11d0, 0x82, 0x22, 0, 0x60, 0x97, 0x93, 0x87, 0xea);

```

#### <a name="iidimapigetsession"></a><span data-ttu-id="dd148-471">IID_IMAPIGetSession</span><span class="sxs-lookup"><span data-stu-id="dd148-471">IID_IMAPIGetSession</span></span>
  
```cpp
DEFINE_GUID(IID_IMAPIGetSession, 0x614ab435, 0x491d, 0x4f5b, 0xa8, 0xb4, 0x60, 0xeb, 0x3, 0x10, 0x30, 0xc6);

```

### <a name="pst-override-handler-interface-identifiers"></a><span data-ttu-id="dd148-472">PST 重写处理程序界面标识符</span><span class="sxs-lookup"><span data-stu-id="dd148-472">PST Override Handler interface identifiers</span></span>

#### <a name="iidipstoverridereq"></a><span data-ttu-id="dd148-473">IID_IPSTOVERRIDEREQ</span><span class="sxs-lookup"><span data-stu-id="dd148-473">IID_IPSTOVERRIDEREQ</span></span>
  
```cpp
// {892EBC6D-24DC-4d90-BA48-C6CBEC14A86A}
DEFINE_GUID(IID_IPSTOVERRIDEREQ, 0x892ebc6d, 0x24dc, 0x4d90, 0xba, 0x48, 0xc6, 0xcb, 0xec, 0x14, 0xa8, 0x6a);
```

#### <a name="iidipstoverride1"></a><span data-ttu-id="dd148-474">IID_IPSTOVERRIDE1</span><span class="sxs-lookup"><span data-stu-id="dd148-474">IID_IPSTOVERRIDE1</span></span>
  
```cpp
// {FBB68D34-F561-44fb-A8CA-AE36696342CA}
DEFINE_GUID(IID_IPSTOVERRIDE1, 0xfbb68d34, 0xf561, 0x44fb, 0xa8, 0xca, 0xae, 0x36, 0x69, 0x63, 0x42, 0xca);
```

## <a name="see-also"></a><span data-ttu-id="dd148-475">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd148-475">See also</span></span>

- [<span data-ttu-id="dd148-476">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="dd148-476">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="dd148-477">关于 Outlook 使用的命名属性</span><span class="sxs-lookup"><span data-stu-id="dd148-477">About Named Properties Used by Outlook</span></span>](about-named-properties-used-by-outlook.md)
- [<span data-ttu-id="dd148-478">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="dd148-478">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="dd148-479">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="dd148-479">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="dd148-480">在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）</span><span class="sxs-lookup"><span data-stu-id="dd148-480">Manage a Message in an OST Without Invoking a Synchronization in Cached Exchange Mode</span></span>](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

