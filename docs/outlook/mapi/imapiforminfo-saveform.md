---
title: IMAPIFormInfoSaveForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.SaveForm
api_type:
- COM
ms.assetid: 18a10f14-0795-4d4d-b590-f4cef4f2902a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e2d757fe329f9a57447723d72a859c7d82fc2b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775414"
---
# <a name="imapiforminfosaveform"></a><span data-ttu-id="690de-103">IMAPIFormInfo::SaveForm</span><span class="sxs-lookup"><span data-stu-id="690de-103">IMAPIFormInfo::SaveForm</span></span>

  
  
<span data-ttu-id="690de-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="690de-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="690de-105">配置文件中保存窗体特定的说明。</span><span class="sxs-lookup"><span data-stu-id="690de-105">Saves a description of a particular form in a configuration file.</span></span>
  
```cpp
HRESULT SaveForm(
  LPCSTR szFileName
);
```

## <a name="parameters"></a><span data-ttu-id="690de-106">参数</span><span class="sxs-lookup"><span data-stu-id="690de-106">Parameters</span></span>

 <span data-ttu-id="690de-107">_szFileName_</span><span class="sxs-lookup"><span data-stu-id="690de-107">_szFileName_</span></span>
  
> <span data-ttu-id="690de-108">[in]命名窗体的说明邮件文件及其说明的保存位置的字符串。</span><span class="sxs-lookup"><span data-stu-id="690de-108">[in] A string that names the form's description message file where its description is saved.</span></span> <span data-ttu-id="690de-109">此文件名称必须具有.fdm 扩展名。</span><span class="sxs-lookup"><span data-stu-id="690de-109">This file name must have the .fdm extension.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="690de-110">返回值</span><span class="sxs-lookup"><span data-stu-id="690de-110">Return value</span></span>

<span data-ttu-id="690de-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="690de-111">S_OK</span></span> 
  
> <span data-ttu-id="690de-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="690de-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="690de-113">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="690de-113">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="690de-114">无法写入配置文件。</span><span class="sxs-lookup"><span data-stu-id="690de-114">The configuration file could not be written.</span></span> <span data-ttu-id="690de-115">要获取与错误关联的[MAPIERROR](mapierror.md)结构，请调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="690de-115">To get the [MAPIERROR](mapierror.md) structure that is associated with the error, call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="690de-116">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="690de-116">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="690de-117">**SaveForm**称为可能要将表单保存在本地窗体容器。</span><span class="sxs-lookup"><span data-stu-id="690de-117">**SaveForm** was probably called to save a form in the local form container.</span></span> <span data-ttu-id="690de-118">本地窗体容器上不支持**SaveForm** 。</span><span class="sxs-lookup"><span data-stu-id="690de-118">**SaveForm** is not supported on the local form container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="690de-119">说明</span><span class="sxs-lookup"><span data-stu-id="690de-119">Remarks</span></span>

<span data-ttu-id="690de-120">客户端应用程序调用**IMAPIFormInfo::SaveForm**方法具有给定的文件名的文件中保存当前表单的说明。</span><span class="sxs-lookup"><span data-stu-id="690de-120">Client applications call the **IMAPIFormInfo::SaveForm** method to save a description of the current form in the file that has the given file name.</span></span> <span data-ttu-id="690de-121">**SaveForm**创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="690de-121">**SaveForm** creates a configuration file.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="690de-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="690de-122">Notes to callers</span></span>

<span data-ttu-id="690de-123">您可以通过从表单库提供程序显示的窗体描述符消息对话框中的列表中选择联系人重新安装窗体。</span><span class="sxs-lookup"><span data-stu-id="690de-123">You can reinstall forms by selecting them from a list of form descriptor messages in a dialog box that form library providers display.</span></span> <span data-ttu-id="690de-124">窗体描述符消息的建议的扩展名是.fdm。</span><span class="sxs-lookup"><span data-stu-id="690de-124">The recommended extension for form descriptor messages is .fdm.</span></span>
  
<span data-ttu-id="690de-125">调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法，如果**SaveForm**返回 MAPI_E_EXTENDED_ERROR，并检查返回的**MAPIERROR**结构，以确定导致出错的条件。</span><span class="sxs-lookup"><span data-stu-id="690de-125">Call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method if **SaveForm** returns MAPI_E_EXTENDED_ERROR, and check the returned **MAPIERROR** structure to determine the condition that caused the error.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="690de-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="690de-126">See also</span></span>



[<span data-ttu-id="690de-127">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="690de-127">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="690de-128">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="690de-128">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="690de-129">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="690de-129">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

