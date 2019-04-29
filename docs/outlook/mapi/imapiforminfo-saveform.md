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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 391ea3ef4f44db2a9d007241232f58db27647ba2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428744"
---
# <a name="imapiforminfosaveform"></a><span data-ttu-id="09278-103">IMAPIFormInfo::SaveForm</span><span class="sxs-lookup"><span data-stu-id="09278-103">IMAPIFormInfo::SaveForm</span></span>

  
  
<span data-ttu-id="09278-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="09278-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="09278-105">在配置文件中保存特定窗体的说明。</span><span class="sxs-lookup"><span data-stu-id="09278-105">Saves a description of a particular form in a configuration file.</span></span>
  
```cpp
HRESULT SaveForm(
  LPCSTR szFileName
);
```

## <a name="parameters"></a><span data-ttu-id="09278-106">参数</span><span class="sxs-lookup"><span data-stu-id="09278-106">Parameters</span></span>

 <span data-ttu-id="09278-107">_szFileName_</span><span class="sxs-lookup"><span data-stu-id="09278-107">_szFileName_</span></span>
  
> <span data-ttu-id="09278-108">实时一个字符串, 用于在保存其说明的位置命名表单的说明邮件文件。</span><span class="sxs-lookup"><span data-stu-id="09278-108">[in] A string that names the form's description message file where its description is saved.</span></span> <span data-ttu-id="09278-109">此文件名必须具有扩展名 fdm。</span><span class="sxs-lookup"><span data-stu-id="09278-109">This file name must have the .fdm extension.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="09278-110">返回值</span><span class="sxs-lookup"><span data-stu-id="09278-110">Return value</span></span>

<span data-ttu-id="09278-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="09278-111">S_OK</span></span> 
  
> <span data-ttu-id="09278-112">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="09278-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="09278-113">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="09278-113">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="09278-114">无法写入配置文件。</span><span class="sxs-lookup"><span data-stu-id="09278-114">The configuration file could not be written.</span></span> <span data-ttu-id="09278-115">若要获取与错误相关联的[MAPIERROR](mapierror.md)结构, 请调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="09278-115">To get the [MAPIERROR](mapierror.md) structure that is associated with the error, call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="09278-116">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="09278-116">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="09278-117">**SaveForm**可能被称为将表单保存在本地表单容器中。</span><span class="sxs-lookup"><span data-stu-id="09278-117">**SaveForm** was probably called to save a form in the local form container.</span></span> <span data-ttu-id="09278-118">本地表单容器上不支持**SaveForm** 。</span><span class="sxs-lookup"><span data-stu-id="09278-118">**SaveForm** is not supported on the local form container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="09278-119">说明</span><span class="sxs-lookup"><span data-stu-id="09278-119">Remarks</span></span>

<span data-ttu-id="09278-120">客户端应用程序调用**IMAPIFormInfo:: SaveForm**方法将当前表单的说明保存在具有给定文件名的文件中。</span><span class="sxs-lookup"><span data-stu-id="09278-120">Client applications call the **IMAPIFormInfo::SaveForm** method to save a description of the current form in the file that has the given file name.</span></span> <span data-ttu-id="09278-121">**SaveForm**创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="09278-121">**SaveForm** creates a configuration file.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="09278-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="09278-122">Notes to callers</span></span>

<span data-ttu-id="09278-123">您可以通过在表单库提供程序显示的对话框中从表单描述符消息列表中进行选择来重新安装表单。</span><span class="sxs-lookup"><span data-stu-id="09278-123">You can reinstall forms by selecting them from a list of form descriptor messages in a dialog box that form library providers display.</span></span> <span data-ttu-id="09278-124">推荐的窗体描述符消息扩展名为 fdm。</span><span class="sxs-lookup"><span data-stu-id="09278-124">The recommended extension for form descriptor messages is .fdm.</span></span>
  
<span data-ttu-id="09278-125">如果**SaveForm**返回 MAPI_E_EXTENDED_ERROR, 则调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法, 然后检查返回的**MAPIERROR**结构以确定导致错误的条件。</span><span class="sxs-lookup"><span data-stu-id="09278-125">Call the [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method if **SaveForm** returns MAPI_E_EXTENDED_ERROR, and check the returned **MAPIERROR** structure to determine the condition that caused the error.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="09278-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09278-126">See also</span></span>



[<span data-ttu-id="09278-127">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="09278-127">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="09278-128">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="09278-128">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="09278-129">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="09278-129">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

