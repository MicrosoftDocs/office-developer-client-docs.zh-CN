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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9e22111ec920d89e0874baf71946681c204cacd5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571204"
---
# <a name="iprofadmincopyprofile"></a><span data-ttu-id="a6b7a-103">IProfAdmin::CopyProfile</span><span class="sxs-lookup"><span data-stu-id="a6b7a-103">IProfAdmin::CopyProfile</span></span>

  
  
<span data-ttu-id="a6b7a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6b7a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6b7a-105">一个配置文件的副本。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-105">Copies a profile.</span></span>
  
```cpp
HRESULTCopyProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a6b7a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a6b7a-106">Parameters</span></span>

 <span data-ttu-id="a6b7a-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="a6b7a-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="a6b7a-108">[in]一个指向要复制的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-108">[in] A pointer to the name of the profile to copy.</span></span>
    
 <span data-ttu-id="a6b7a-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="a6b7a-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="a6b7a-110">[in]指向要复制的配置文件的密码的指针。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-110">[in] A pointer to the password of the profile to copy.</span></span>
    
 <span data-ttu-id="a6b7a-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="a6b7a-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="a6b7a-112">[in]一个指向复制的配置文件的新名称。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-112">[in] A pointer to the new name of the copied profile.</span></span>
    
 <span data-ttu-id="a6b7a-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a6b7a-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="a6b7a-114">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="a6b7a-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a6b7a-115">_ulFlags_</span></span>
  
> <span data-ttu-id="a6b7a-116">[in]位掩码的标志，控制如何复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-116">[in] A bitmask of flags that controls how the profile is copied.</span></span> <span data-ttu-id="a6b7a-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a6b7a-117">The following flags can be set:</span></span>
    
<span data-ttu-id="a6b7a-118">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a6b7a-118">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="a6b7a-119">显示一个对话框，提示用户输入正确的密码的配置文件复制。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-119">Displays a dialog box that prompts the user for the correct password of the profile to copy.</span></span> <span data-ttu-id="a6b7a-120">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-120">If this flag is not set, no dialog box is displayed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a6b7a-121">返回值</span><span class="sxs-lookup"><span data-stu-id="a6b7a-121">Return value</span></span>

<span data-ttu-id="a6b7a-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6b7a-122">S_OK</span></span> 
  
> <span data-ttu-id="a6b7a-123">配置文件成功复制。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-123">The profile was successfully copied.</span></span>
    
<span data-ttu-id="a6b7a-124">MAPI_E_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="a6b7a-124">MAPI_E_ACCESS_DENIED</span></span> 
  
> <span data-ttu-id="a6b7a-125">与现有的配置文件的相同的新配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-125">The new profile name is the same as that of an existing profile.</span></span>
    
<span data-ttu-id="a6b7a-126">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="a6b7a-126">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="a6b7a-127">要复制的配置文件的密码不正确，并向用户请求正确的密码，因为_ulFlags_参数中未设置 MAPI_DIALOG 无法显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-127">The password for the profile to copy is incorrect, and a dialog box could not be displayed to the user to request the correct password because MAPI_DIALOG was not set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="a6b7a-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a6b7a-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="a6b7a-129">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-129">The specified profile does not exist.</span></span>
    
<span data-ttu-id="a6b7a-130">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="a6b7a-130">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="a6b7a-131">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-131">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a6b7a-132">注解</span><span class="sxs-lookup"><span data-stu-id="a6b7a-132">Remarks</span></span>

<span data-ttu-id="a6b7a-133">由指向_lpszOldProfileName_，将其命名配置文件的副本所指的_lpszNewProfileName_ **IProfAdmin::CopyProfile**方法使。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-133">The **IProfAdmin::CopyProfile** method makes a copy of the profile pointed to by  _lpszOldProfileName_, giving it the name pointed to by  _lpszNewProfileName_.</span></span> <span data-ttu-id="a6b7a-134">将配置文件复制留副本与原始相同的密码。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-134">Copying a profile leaves the copy with the same password as the original.</span></span>
  
<span data-ttu-id="a6b7a-135">原始的配置文件、 其密码和副本的名称的长度最多为 64 个字符，并可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="a6b7a-135">The name of the original profile, its password, and the copy can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="a6b7a-136">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-136">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="a6b7a-137">嵌入的空格，但不是前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-137">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="a6b7a-138">在所有操作系统上不支持配置文件密码。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-138">Profile passwords are not supported on all operating systems.</span></span> <span data-ttu-id="a6b7a-139">在操作系统上不支持配置文件密码， _lpszOldPassword_可以为 NULL 或为零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-139">On operating systems that do not support profile passwords,  _lpszOldPassword_ can be NULL or a pointer to a zero-length string.</span></span> 
  
<span data-ttu-id="a6b7a-140">_LpszOldPassword_设置为 NULL，如果要复制的配置文件需要密码，并设置了 MAPI_DIALOG 标志;显示一个对话框，提示用户提供密码。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-140">If  _lpszOldPassword_ is set to NULL, the profile to be copied requires a password, and the MAPI_DIALOG flag is set; a dialog box that prompts the user to provide the password is displayed.</span></span> <span data-ttu-id="a6b7a-141">如果密码是必需的但_lpszOldPassword_设置为 NULL，未设置 MAPI_DIALOG 标志**CopyProfile**返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="a6b7a-141">If a password is required, but  _lpszOldPassword_ is set to NULL and the MAPI_DIALOG flag is not set, **CopyProfile** returns MAPI_E_LOGON_FAILED.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a6b7a-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6b7a-142">See also</span></span>



[<span data-ttu-id="a6b7a-143">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a6b7a-143">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

