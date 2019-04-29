---
title: IProfAdminCopyProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.CopyProfile
api_type:
- COM
ms.assetid: f4846dc3-0236-44ed-a1b1-8c13d48fb58a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c3c4ac10003aad8949de94e0f144410af10078b1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437236"
---
# <a name="iprofadmincopyprofile"></a><span data-ttu-id="49e95-103">IProfAdmin::CopyProfile</span><span class="sxs-lookup"><span data-stu-id="49e95-103">IProfAdmin::CopyProfile</span></span>

  
  
<span data-ttu-id="49e95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49e95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49e95-105">复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="49e95-105">Copies a profile.</span></span>
  
```cpp
HRESULTCopyProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="49e95-106">参数</span><span class="sxs-lookup"><span data-stu-id="49e95-106">Parameters</span></span>

 <span data-ttu-id="49e95-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="49e95-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="49e95-108">实时指向要复制的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="49e95-108">[in] A pointer to the name of the profile to copy.</span></span>
    
 <span data-ttu-id="49e95-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="49e95-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="49e95-110">实时指向要复制的配置文件的密码的指针。</span><span class="sxs-lookup"><span data-stu-id="49e95-110">[in] A pointer to the password of the profile to copy.</span></span>
    
 <span data-ttu-id="49e95-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="49e95-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="49e95-112">实时指向复制的配置文件的新名称的指针。</span><span class="sxs-lookup"><span data-stu-id="49e95-112">[in] A pointer to the new name of the copied profile.</span></span>
    
 <span data-ttu-id="49e95-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="49e95-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="49e95-114">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="49e95-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="49e95-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="49e95-115">_ulFlags_</span></span>
  
> <span data-ttu-id="49e95-116">实时用于控制如何复制配置文件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="49e95-116">[in] A bitmask of flags that controls how the profile is copied.</span></span> <span data-ttu-id="49e95-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="49e95-117">The following flags can be set:</span></span>
    
<span data-ttu-id="49e95-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="49e95-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="49e95-119">显示一个对话框, 提示用户输入要复制的配置文件的正确密码。</span><span class="sxs-lookup"><span data-stu-id="49e95-119">Displays a dialog box that prompts the user for the correct password of the profile to copy.</span></span> <span data-ttu-id="49e95-120">如果未设置此标志, 则不会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="49e95-120">If this flag is not set, no dialog box is displayed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="49e95-121">返回值</span><span class="sxs-lookup"><span data-stu-id="49e95-121">Return value</span></span>

<span data-ttu-id="49e95-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="49e95-122">S_OK</span></span> 
  
> <span data-ttu-id="49e95-123">已成功复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="49e95-123">The profile was successfully copied.</span></span>
    
<span data-ttu-id="49e95-124">MAPI_E_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="49e95-124">MAPI_E_ACCESS_DENIED</span></span> 
  
> <span data-ttu-id="49e95-125">新配置文件的名称与现有配置文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="49e95-125">The new profile name is the same as that of an existing profile.</span></span>
    
<span data-ttu-id="49e95-126">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="49e95-126">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="49e95-127">要复制的配置文件的密码不正确, 并且无法向用户显示对话框来请求正确的密码, 因为未在_ulFlags_参数中设置 MAPI_DIALOG。</span><span class="sxs-lookup"><span data-stu-id="49e95-127">The password for the profile to copy is incorrect, and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="49e95-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="49e95-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="49e95-129">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="49e95-129">The specified profile does not exist.</span></span>
    
<span data-ttu-id="49e95-130">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="49e95-130">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="49e95-131">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="49e95-131">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="49e95-132">说明</span><span class="sxs-lookup"><span data-stu-id="49e95-132">Remarks</span></span>

<span data-ttu-id="49e95-133">**IProfAdmin:: CopyProfile**方法创建由_lpszOldProfileName_指向的配置文件的副本, 并为其提供_lpszNewProfileName_指向的名称。</span><span class="sxs-lookup"><span data-stu-id="49e95-133">The **IProfAdmin::CopyProfile** method makes a copy of the profile pointed to by  _lpszOldProfileName_, giving it the name pointed to by  _lpszNewProfileName_.</span></span> <span data-ttu-id="49e95-134">复制配置文件会保留副本与原始文件相同的密码。</span><span class="sxs-lookup"><span data-stu-id="49e95-134">Copying a profile leaves the copy with the same password as the original.</span></span>
  
<span data-ttu-id="49e95-135">原始配置文件的名称、其密码和副本的长度最高为64个字符, 并且可以包含以下字符:</span><span class="sxs-lookup"><span data-stu-id="49e95-135">The name of the original profile, its password, and the copy can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="49e95-136">所有字母数字字符, 包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="49e95-136">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="49e95-137">嵌入空格, 但不能是前导空格或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="49e95-137">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="49e95-138">配置文件密码在所有操作系统上均不受支持。</span><span class="sxs-lookup"><span data-stu-id="49e95-138">Profile passwords are not supported on all operating systems.</span></span> <span data-ttu-id="49e95-139">在不支持配置文件密码的操作系统上, _lpszOldPassword_可以是 NULL, 也可以是指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="49e95-139">On operating systems that do not support profile passwords,  _lpszOldPassword_ can be NULL or a pointer to a zero-length string.</span></span> 
  
<span data-ttu-id="49e95-140">如果将_lpszOldPassword_设置为 NULL, 要复制的配置文件需要密码, 并且设置了 MAPI_DIALOG 标志;将显示一个对话框, 提示用户提供密码。</span><span class="sxs-lookup"><span data-stu-id="49e95-140">If  _lpszOldPassword_ is set to NULL, the profile to be copied requires a password, and the MAPI_DIALOG flag is set; a dialog box that prompts the user to provide the password is displayed.</span></span> <span data-ttu-id="49e95-141">如果需要密码, 但_lpszOldPassword_设置为 NULL, 并且未设置 MAPI_DIALOG 标志, 则**CopyProfile**将返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="49e95-141">If a password is required, but  _lpszOldPassword_ is set to NULL and the MAPI_DIALOG flag is not set, **CopyProfile** returns MAPI_E_LOGON_FAILED.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="49e95-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49e95-142">See also</span></span>



[<span data-ttu-id="49e95-143">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="49e95-143">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

