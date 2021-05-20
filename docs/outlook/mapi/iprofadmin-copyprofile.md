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
# <a name="iprofadmincopyprofile"></a><span data-ttu-id="12471-103">IProfAdmin::CopyProfile</span><span class="sxs-lookup"><span data-stu-id="12471-103">IProfAdmin::CopyProfile</span></span>

  
  
<span data-ttu-id="12471-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12471-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12471-105">复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="12471-105">Copies a profile.</span></span>
  
```cpp
HRESULTCopyProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="12471-106">参数</span><span class="sxs-lookup"><span data-stu-id="12471-106">Parameters</span></span>

 <span data-ttu-id="12471-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="12471-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="12471-108">[in]指向要复制的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="12471-108">[in] A pointer to the name of the profile to copy.</span></span>
    
 <span data-ttu-id="12471-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="12471-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="12471-110">[in]指向要复制的配置文件的密码的指针。</span><span class="sxs-lookup"><span data-stu-id="12471-110">[in] A pointer to the password of the profile to copy.</span></span>
    
 <span data-ttu-id="12471-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="12471-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="12471-112">[in]指向复制的配置文件的新名称的指针。</span><span class="sxs-lookup"><span data-stu-id="12471-112">[in] A pointer to the new name of the copied profile.</span></span>
    
 <span data-ttu-id="12471-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="12471-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="12471-114">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="12471-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="12471-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="12471-115">_ulFlags_</span></span>
  
> <span data-ttu-id="12471-116">[in]控制配置文件复制方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="12471-116">[in] A bitmask of flags that controls how the profile is copied.</span></span> <span data-ttu-id="12471-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="12471-117">The following flags can be set:</span></span>
    
<span data-ttu-id="12471-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="12471-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="12471-119">显示一个对话框，提示用户输入要复制的配置文件的正确密码。</span><span class="sxs-lookup"><span data-stu-id="12471-119">Displays a dialog box that prompts the user for the correct password of the profile to copy.</span></span> <span data-ttu-id="12471-120">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="12471-120">If this flag is not set, no dialog box is displayed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="12471-121">返回值</span><span class="sxs-lookup"><span data-stu-id="12471-121">Return value</span></span>

<span data-ttu-id="12471-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="12471-122">S_OK</span></span> 
  
> <span data-ttu-id="12471-123">已成功复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="12471-123">The profile was successfully copied.</span></span>
    
<span data-ttu-id="12471-124">MAPI_E_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="12471-124">MAPI_E_ACCESS_DENIED</span></span> 
  
> <span data-ttu-id="12471-125">新配置文件名称与现有配置文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="12471-125">The new profile name is the same as that of an existing profile.</span></span>
    
<span data-ttu-id="12471-126">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="12471-126">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="12471-127">要复制的配置文件的密码不正确，并且无法向用户显示一个对话框来请求正确的密码，因为 MAPI_DIALOG  _ulFlags_ 参数中未设置该密码。</span><span class="sxs-lookup"><span data-stu-id="12471-127">The password for the profile to copy is incorrect, and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="12471-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="12471-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="12471-129">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="12471-129">The specified profile does not exist.</span></span>
    
<span data-ttu-id="12471-130">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="12471-130">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="12471-131">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="12471-131">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="12471-132">备注</span><span class="sxs-lookup"><span data-stu-id="12471-132">Remarks</span></span>

<span data-ttu-id="12471-133">**IProfAdmin：：CopyProfile** 方法创建 _lpszOldProfileName_ 指向的配置文件的副本，并指定 _lpszNewProfileName_ 指向的名称。</span><span class="sxs-lookup"><span data-stu-id="12471-133">The **IProfAdmin::CopyProfile** method makes a copy of the profile pointed to by  _lpszOldProfileName_, giving it the name pointed to by  _lpszNewProfileName_.</span></span> <span data-ttu-id="12471-134">复制配置文件会保留副本与原始副本相同的密码。</span><span class="sxs-lookup"><span data-stu-id="12471-134">Copying a profile leaves the copy with the same password as the original.</span></span>
  
<span data-ttu-id="12471-135">原始配置文件的名称、其密码和副本的长度最多为 64 个字符，可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="12471-135">The name of the original profile, its password, and the copy can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="12471-136">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="12471-136">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="12471-137">嵌入空格，但不包括前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="12471-137">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="12471-138">配置文件密码并非在所有操作系统上都受支持。</span><span class="sxs-lookup"><span data-stu-id="12471-138">Profile passwords are not supported on all operating systems.</span></span> <span data-ttu-id="12471-139">在不支持配置文件密码的操作系统上  _，lpszOldPassword_ 可以是 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="12471-139">On operating systems that do not support profile passwords,  _lpszOldPassword_ can be NULL or a pointer to a zero-length string.</span></span> 
  
<span data-ttu-id="12471-140">如果  _lpszOldPassword_ 设置为 NULL，则要复制的配置文件需要密码，并设置MAPI_DIALOG标记;将显示提示用户输入密码的对话框。</span><span class="sxs-lookup"><span data-stu-id="12471-140">If  _lpszOldPassword_ is set to NULL, the profile to be copied requires a password, and the MAPI_DIALOG flag is set; a dialog box that prompts the user to provide the password is displayed.</span></span> <span data-ttu-id="12471-141">如果需要密码，但  _lpszOldPassword_ 设置为 NULL，并且未设置 MAPI_DIALOG 标志 **，CopyProfile** 将返回MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="12471-141">If a password is required, but  _lpszOldPassword_ is set to NULL and the MAPI_DIALOG flag is not set, **CopyProfile** returns MAPI_E_LOGON_FAILED.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="12471-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12471-142">See also</span></span>



[<span data-ttu-id="12471-143">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="12471-143">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

