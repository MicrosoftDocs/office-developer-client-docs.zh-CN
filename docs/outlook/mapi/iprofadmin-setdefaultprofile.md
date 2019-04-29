---
title: IProfAdminSetDefaultProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.SetDefaultProfile
api_type:
- COM
ms.assetid: 58f50535-b0ed-4097-bda8-fd3ccc2d4b49
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 44be43864d943257520f27297e5754a4978c568d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439623"
---
# <a name="iprofadminsetdefaultprofile"></a><span data-ttu-id="7ca2a-103">IProfAdmin::SetDefaultProfile</span><span class="sxs-lookup"><span data-stu-id="7ca2a-103">IProfAdmin::SetDefaultProfile</span></span>

  
  
<span data-ttu-id="7ca2a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ca2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ca2a-105">设置或清除客户端的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-105">Sets or clears a client's default profile.</span></span>
  
```cpp
HRESULT SetDefaultProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="7ca2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="7ca2a-106">Parameters</span></span>

 <span data-ttu-id="7ca2a-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="7ca2a-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="7ca2a-108">实时指向将成为默认值的配置文件的名称的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-108">[in] A pointer to the name of the profile that will become the default, or NULL.</span></span> <span data-ttu-id="7ca2a-109">将_lpszProfileName_设置为 NULL 表示**SetDefaultProfile**应删除现有的默认配置文件, 使客户端不使用默认配置。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-109">Setting  _lpszProfileName_ to NULL indicates that **SetDefaultProfile** should remove the existing default profile, leaving the client without a default.</span></span> 
    
 <span data-ttu-id="7ca2a-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7ca2a-110">_ulFlags_</span></span>
  
> <span data-ttu-id="7ca2a-111">实时标志的位掩码, 用于控制由_lpszProfileName_指向的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-111">[in] A bitmask of flags that controls the type of the string pointed to by  _lpszProfileName_.</span></span> <span data-ttu-id="7ca2a-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="7ca2a-112">The following flag can be set:</span></span>
    
<span data-ttu-id="7ca2a-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7ca2a-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="7ca2a-114">配置文件名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-114">The profile name is in Unicode format.</span></span> <span data-ttu-id="7ca2a-115">如果未设置 MAPI_UNICODE 标志, 则配置文件名称将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-115">If the MAPI_UNICODE flag is not set, the profile name is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7ca2a-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7ca2a-116">Return value</span></span>

<span data-ttu-id="7ca2a-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ca2a-117">S_OK</span></span> 
  
> <span data-ttu-id="7ca2a-118">已成功建立或删除了默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-118">A default profile was successfully established or removed.</span></span>
    
<span data-ttu-id="7ca2a-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7ca2a-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="7ca2a-120">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-120">The specified profile does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ca2a-121">说明</span><span class="sxs-lookup"><span data-stu-id="7ca2a-121">Remarks</span></span>

<span data-ttu-id="7ca2a-122">**IProfAdmin:: SetDefaultProfile**方法要么将特定配置文件建立为客户端的默认配置文件, 要么清除当前的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-122">The **IProfAdmin::SetDefaultProfile** method either establishes a particular profile as the client's default profile or clears the current default profile.</span></span> <span data-ttu-id="7ca2a-123">默认配置文件是在客户端开始 MAPI 会话时自动使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-123">The default profile is the profile that is automatically used whenever the client begins a MAPI session.</span></span> <span data-ttu-id="7ca2a-124">**SetDefaultProfile**还将新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-124">**SetDefaultProfile** also sets the new default profile's **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) property to TRUE.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7ca2a-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7ca2a-125">Notes to callers</span></span>

<span data-ttu-id="7ca2a-126">若要使用默认配置文件启动会话, 请将 MAPI_USE_DEFAULT 标志传递给[MAPILogonEx](mapilogonex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="7ca2a-126">To start a session with the default profile, pass the MAPI_USE_DEFAULT flag to the [MAPILogonEx](mapilogonex.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ca2a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ca2a-127">See also</span></span>



[<span data-ttu-id="7ca2a-128">IProfAdmin::GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="7ca2a-128">IProfAdmin::GetProfileTable</span></span>](iprofadmin-getprofiletable.md)
  
[<span data-ttu-id="7ca2a-129">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="7ca2a-129">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="7ca2a-130">PidTagDefaultProfile 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ca2a-130">PidTagDefaultProfile Canonical Property</span></span>](pidtagdefaultprofile-canonical-property.md)
  
[<span data-ttu-id="7ca2a-131">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7ca2a-131">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

