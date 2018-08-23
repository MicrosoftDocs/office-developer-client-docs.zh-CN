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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4453465c04d7a5a3de79f2ae34d13095863487cf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569503"
---
# <a name="iprofadminrenameprofile"></a><span data-ttu-id="be3cc-103">IProfAdmin::RenameProfile</span><span class="sxs-lookup"><span data-stu-id="be3cc-103">IProfAdmin::RenameProfile</span></span>

  
  
<span data-ttu-id="be3cc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be3cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be3cc-105">向一个配置文件分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-105">Assigns a new name to a profile.</span></span>
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="be3cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="be3cc-106">Parameters</span></span>

 <span data-ttu-id="be3cc-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="be3cc-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="be3cc-108">[in]一个指向当前重命名的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-108">[in] A pointer to the current name of the profile to rename.</span></span>
    
 <span data-ttu-id="be3cc-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="be3cc-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="be3cc-110">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="be3cc-110">[in] Always NULL.</span></span>
    
 <span data-ttu-id="be3cc-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="be3cc-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="be3cc-112">[in]一个指向重命名的配置文件的新名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-112">[in] A pointer to the new name of the profile to rename.</span></span>
    
 <span data-ttu-id="be3cc-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="be3cc-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="be3cc-114">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="be3cc-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> 
    
 <span data-ttu-id="be3cc-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="be3cc-115">_ulFlags_</span></span>
  
> <span data-ttu-id="be3cc-116">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="be3cc-116">[in] Always NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="be3cc-117">返回值</span><span class="sxs-lookup"><span data-stu-id="be3cc-117">Return value</span></span>

<span data-ttu-id="be3cc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="be3cc-118">S_OK</span></span> 
  
> <span data-ttu-id="be3cc-119">已成功重命名配置文件。</span><span class="sxs-lookup"><span data-stu-id="be3cc-119">The profile was successfully renamed.</span></span>
    
<span data-ttu-id="be3cc-120">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="be3cc-120">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="be3cc-121">配置文件密码不正确。</span><span class="sxs-lookup"><span data-stu-id="be3cc-121">The profile password is incorrect.</span></span>
    
<span data-ttu-id="be3cc-122">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="be3cc-122">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="be3cc-123">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="be3cc-123">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="be3cc-124">注解</span><span class="sxs-lookup"><span data-stu-id="be3cc-124">Remarks</span></span>

<span data-ttu-id="be3cc-125">如果有的话， **IProfAdmin::RenameProfile**方法向一个配置文件指定一个新名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-125">The **IProfAdmin::RenameProfile** method assigns a new name to a profile, if it has one.</span></span> <span data-ttu-id="be3cc-126">如果要重命名的配置文件，使用客户端调用**RenameProfile**时**RenameProfile**标记配置文件，并返回 S_OK 而不是使用配置文件时，尝试重命名操作。</span><span class="sxs-lookup"><span data-stu-id="be3cc-126">If the profile to rename is in use by a client when **RenameProfile** is called, **RenameProfile** marks the profile and returns S_OK instead of attempting the rename operation while the profile is in use.</span></span> <span data-ttu-id="be3cc-127">不再使用配置文件时， **RenameProfile**将其分配的新名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-127">When the profile is no longer being used, **RenameProfile** assigns it the new name.</span></span> 
  
<span data-ttu-id="be3cc-128">旧的和新的配置文件的名称可以是最多为 64 个字符的长度，并且可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="be3cc-128">The old and new names of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="be3cc-129">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="be3cc-129">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="be3cc-130">嵌入的空格，但不是前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="be3cc-130">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="be3cc-131">_LpszPassword_应始终为 NULL 或为零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="be3cc-131">The  _lpszPassword_ should always be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="be3cc-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be3cc-132">See also</span></span>



[<span data-ttu-id="be3cc-133">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="be3cc-133">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

