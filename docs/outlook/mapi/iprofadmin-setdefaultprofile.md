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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270166"
---
# <a name="iprofadminsetdefaultprofile"></a><span data-ttu-id="86779-103">IProfAdmin::SetDefaultProfile</span><span class="sxs-lookup"><span data-stu-id="86779-103">IProfAdmin::SetDefaultProfile</span></span>

  
  
<span data-ttu-id="86779-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86779-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86779-105">设置或清除客户端的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="86779-105">Sets or clears a client's default profile.</span></span>
  
```cpp
HRESULT SetDefaultProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="86779-106">参数</span><span class="sxs-lookup"><span data-stu-id="86779-106">Parameters</span></span>

 <span data-ttu-id="86779-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="86779-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="86779-108">实时指向将成为默认值的配置文件的名称的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="86779-108">[in] A pointer to the name of the profile that will become the default, or NULL.</span></span> <span data-ttu-id="86779-109">将_lpszProfileName_设置为 NULL 表示**SetDefaultProfile**应删除现有的默认配置文件, 使客户端不使用默认配置。</span><span class="sxs-lookup"><span data-stu-id="86779-109">Setting  _lpszProfileName_ to NULL indicates that **SetDefaultProfile** should remove the existing default profile, leaving the client without a default.</span></span> 
    
 <span data-ttu-id="86779-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="86779-110">_ulFlags_</span></span>
  
> <span data-ttu-id="86779-111">实时标志的位掩码, 用于控制由_lpszProfileName_指向的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="86779-111">[in] A bitmask of flags that controls the type of the string pointed to by  _lpszProfileName_.</span></span> <span data-ttu-id="86779-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="86779-112">The following flag can be set:</span></span>
    
<span data-ttu-id="86779-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="86779-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="86779-114">配置文件名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="86779-114">The profile name is in Unicode format.</span></span> <span data-ttu-id="86779-115">如果未设置 MAPI_UNICODE 标志, 则配置文件名称将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="86779-115">If the MAPI_UNICODE flag is not set, the profile name is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="86779-116">返回值</span><span class="sxs-lookup"><span data-stu-id="86779-116">Return value</span></span>

<span data-ttu-id="86779-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="86779-117">S_OK</span></span> 
  
> <span data-ttu-id="86779-118">已成功建立或删除了默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="86779-118">A default profile was successfully established or removed.</span></span>
    
<span data-ttu-id="86779-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="86779-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="86779-120">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="86779-120">The specified profile does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="86779-121">注解</span><span class="sxs-lookup"><span data-stu-id="86779-121">Remarks</span></span>

<span data-ttu-id="86779-122">**IProfAdmin:: SetDefaultProfile**方法要么将特定配置文件建立为客户端的默认配置文件, 要么清除当前的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="86779-122">The **IProfAdmin::SetDefaultProfile** method either establishes a particular profile as the client's default profile or clears the current default profile.</span></span> <span data-ttu-id="86779-123">默认配置文件是在客户端开始 MAPI 会话时自动使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="86779-123">The default profile is the profile that is automatically used whenever the client begins a MAPI session.</span></span> <span data-ttu-id="86779-124">**SetDefaultProfile**还将新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="86779-124">**SetDefaultProfile** also sets the new default profile's **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) property to TRUE.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="86779-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="86779-125">Notes to callers</span></span>

<span data-ttu-id="86779-126">若要使用默认配置文件启动会话, 请将 MAPI_USE_DEFAULT 标志传递给[MAPILogonEx](mapilogonex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="86779-126">To start a session with the default profile, pass the MAPI_USE_DEFAULT flag to the [MAPILogonEx](mapilogonex.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="86779-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86779-127">See also</span></span>



[<span data-ttu-id="86779-128">IProfAdmin::GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="86779-128">IProfAdmin::GetProfileTable</span></span>](iprofadmin-getprofiletable.md)
  
[<span data-ttu-id="86779-129">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="86779-129">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="86779-130">PidTagDefaultProfile 规范属性</span><span class="sxs-lookup"><span data-stu-id="86779-130">PidTagDefaultProfile Canonical Property</span></span>](pidtagdefaultprofile-canonical-property.md)
  
[<span data-ttu-id="86779-131">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="86779-131">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

