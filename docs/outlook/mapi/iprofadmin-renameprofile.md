---
title: IProfAdminRenameProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.RenameProfile
api_type:
- COM
ms.assetid: 2a575cac-dbfd-4f42-9c10-4b7e355a065e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 162f20485fc21cf8523b6d4a653e52c35f4b3d9a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317078"
---
# <a name="iprofadminrenameprofile"></a><span data-ttu-id="ff6e5-103">IProfAdmin::RenameProfile</span><span class="sxs-lookup"><span data-stu-id="ff6e5-103">IProfAdmin::RenameProfile</span></span>

  
  
<span data-ttu-id="ff6e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff6e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff6e5-105">为配置文件分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-105">Assigns a new name to a profile.</span></span>
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ff6e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff6e5-106">Parameters</span></span>

 <span data-ttu-id="ff6e5-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="ff6e5-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="ff6e5-108">实时指向要重命名的配置文件的当前名称的指针。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-108">[in] A pointer to the current name of the profile to rename.</span></span>
    
 <span data-ttu-id="ff6e5-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="ff6e5-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="ff6e5-110">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-110">[in] Always NULL.</span></span>
    
 <span data-ttu-id="ff6e5-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="ff6e5-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="ff6e5-112">实时指向要重命名的配置文件的新名称的指针。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-112">[in] A pointer to the new name of the profile to rename.</span></span>
    
 <span data-ttu-id="ff6e5-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ff6e5-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="ff6e5-114">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> 
    
 <span data-ttu-id="ff6e5-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ff6e5-115">_ulFlags_</span></span>
  
> <span data-ttu-id="ff6e5-116">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-116">[in] Always NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ff6e5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ff6e5-117">Return value</span></span>

<span data-ttu-id="ff6e5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff6e5-118">S_OK</span></span> 
  
> <span data-ttu-id="ff6e5-119">已成功重命名配置文件。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-119">The profile was successfully renamed.</span></span>
    
<span data-ttu-id="ff6e5-120">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="ff6e5-120">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="ff6e5-121">配置文件密码不正确。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-121">The profile password is incorrect.</span></span>
    
<span data-ttu-id="ff6e5-122">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ff6e5-122">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="ff6e5-123">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-123">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ff6e5-124">注解</span><span class="sxs-lookup"><span data-stu-id="ff6e5-124">Remarks</span></span>

<span data-ttu-id="ff6e5-125">**IProfAdmin:: RenameProfile**方法将新名称分配给配置文件 (如果有的话)。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-125">The **IProfAdmin::RenameProfile** method assigns a new name to a profile, if it has one.</span></span> <span data-ttu-id="ff6e5-126">如果调用**RenameProfile**时, 客户端正在使用重命名的配置文件, **RenameProfile**将标记配置文件并返回 S_OK, 而不是在配置文件正在使用时尝试重命名操作。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-126">If the profile to rename is in use by a client when **RenameProfile** is called, **RenameProfile** marks the profile and returns S_OK instead of attempting the rename operation while the profile is in use.</span></span> <span data-ttu-id="ff6e5-127">不再使用该配置文件时, **RenameProfile**会为其分配新名称。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-127">When the profile is no longer being used, **RenameProfile** assigns it the new name.</span></span> 
  
<span data-ttu-id="ff6e5-128">配置文件的旧名称和新名称的长度最高为64个字符, 并且可以包含以下字符:</span><span class="sxs-lookup"><span data-stu-id="ff6e5-128">The old and new names of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="ff6e5-129">所有字母数字字符, 包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-129">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="ff6e5-130">嵌入空格, 但不能是前导空格或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-130">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="ff6e5-131">_lpszPassword_应始终为 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-131">The  _lpszPassword_ should always be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ff6e5-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff6e5-132">See also</span></span>



[<span data-ttu-id="ff6e5-133">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ff6e5-133">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

