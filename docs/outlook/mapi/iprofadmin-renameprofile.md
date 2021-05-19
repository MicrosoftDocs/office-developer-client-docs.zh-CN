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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419518"
---
# <a name="iprofadminrenameprofile"></a><span data-ttu-id="0f7cc-103">IProfAdmin::RenameProfile</span><span class="sxs-lookup"><span data-stu-id="0f7cc-103">IProfAdmin::RenameProfile</span></span>

  
  
<span data-ttu-id="0f7cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f7cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f7cc-105">向配置文件分配新名称。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-105">Assigns a new name to a profile.</span></span>
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="0f7cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="0f7cc-106">Parameters</span></span>

 <span data-ttu-id="0f7cc-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="0f7cc-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="0f7cc-108">[in]指向要重命名的配置文件的当前名称的指针。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-108">[in] A pointer to the current name of the profile to rename.</span></span>
    
 <span data-ttu-id="0f7cc-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="0f7cc-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="0f7cc-110">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-110">[in] Always NULL.</span></span>
    
 <span data-ttu-id="0f7cc-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="0f7cc-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="0f7cc-112">[in]指向要重命名的配置文件的新名称的指针。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-112">[in] A pointer to the new name of the profile to rename.</span></span>
    
 <span data-ttu-id="0f7cc-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="0f7cc-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="0f7cc-114">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> 
    
 <span data-ttu-id="0f7cc-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0f7cc-115">_ulFlags_</span></span>
  
> <span data-ttu-id="0f7cc-116">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-116">[in] Always NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0f7cc-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0f7cc-117">Return value</span></span>

<span data-ttu-id="0f7cc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f7cc-118">S_OK</span></span> 
  
> <span data-ttu-id="0f7cc-119">配置文件已成功重命名。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-119">The profile was successfully renamed.</span></span>
    
<span data-ttu-id="0f7cc-120">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="0f7cc-120">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="0f7cc-121">配置文件密码不正确。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-121">The profile password is incorrect.</span></span>
    
<span data-ttu-id="0f7cc-122">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="0f7cc-122">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="0f7cc-123">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-123">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0f7cc-124">备注</span><span class="sxs-lookup"><span data-stu-id="0f7cc-124">Remarks</span></span>

<span data-ttu-id="0f7cc-125">**IProfAdmin：：RenameProfile** 方法为配置文件分配一个新名称（如果有）。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-125">The **IProfAdmin::RenameProfile** method assigns a new name to a profile, if it has one.</span></span> <span data-ttu-id="0f7cc-126">如果在调用 **RenameProfile** 时要重命名的配置文件正由客户端使用 **，RenameProfile** 将标记该配置文件并返回 S_OK 而不是在使用配置文件时尝试重命名操作。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-126">If the profile to rename is in use by a client when **RenameProfile** is called, **RenameProfile** marks the profile and returns S_OK instead of attempting the rename operation while the profile is in use.</span></span> <span data-ttu-id="0f7cc-127">当配置文件不再使用时 **，RenameProfile** 会为其分配新名称。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-127">When the profile is no longer being used, **RenameProfile** assigns it the new name.</span></span> 
  
<span data-ttu-id="0f7cc-128">配置文件的旧名称和新名称的长度最多为 64 个字符，可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="0f7cc-128">The old and new names of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="0f7cc-129">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-129">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="0f7cc-130">嵌入空格，但不包括前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-130">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="0f7cc-131">_lpszPassword_ 应始终为 NULL 或指向零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="0f7cc-131">The  _lpszPassword_ should always be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0f7cc-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f7cc-132">See also</span></span>



[<span data-ttu-id="0f7cc-133">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0f7cc-133">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

