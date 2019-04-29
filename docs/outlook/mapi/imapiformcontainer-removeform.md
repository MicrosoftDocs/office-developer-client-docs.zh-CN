---
title: IMAPIFormContainerRemoveForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.RemoveForm
api_type:
- COM
ms.assetid: 7f851ce8-bd01-4ea5-86e0-e44323cc0aab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e53c0cbd9946ff04516594a7ce99fdc2daf4ff4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432196"
---
# <a name="imapiformcontainerremoveform"></a><span data-ttu-id="a2357-103">IMAPIFormContainer::RemoveForm</span><span class="sxs-lookup"><span data-stu-id="a2357-103">IMAPIFormContainer::RemoveForm</span></span>

  
  
<span data-ttu-id="a2357-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2357-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2357-105">从表单容器中删除特定的窗体。</span><span class="sxs-lookup"><span data-stu-id="a2357-105">Removes a particular form from a form container.</span></span>
  
```cpp
HRESULT RemoveForm(
  LPCSTR szMessageClass
);
```

## <a name="parameters"></a><span data-ttu-id="a2357-106">参数</span><span class="sxs-lookup"><span data-stu-id="a2357-106">Parameters</span></span>

 <span data-ttu-id="a2357-107">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="a2357-107">_szMessageClass_</span></span>
  
> <span data-ttu-id="a2357-108">实时一个字符串, 用于命名要从表单容器中删除的表单的邮件类。</span><span class="sxs-lookup"><span data-stu-id="a2357-108">[in] A string that names the message class of the form to be removed from the form container.</span></span> <span data-ttu-id="a2357-109">邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a2357-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a2357-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a2357-110">Return value</span></span>

<span data-ttu-id="a2357-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2357-111">S_OK</span></span> 
  
> <span data-ttu-id="a2357-112">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a2357-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="a2357-113">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a2357-113">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="a2357-114">在_szMessageClass_参数中传递的邮件类与表单容器中任何表单的邮件类都不匹配。</span><span class="sxs-lookup"><span data-stu-id="a2357-114">The message class passed in the  _szMessageClass_ parameter does not match the message class of any form in the form container.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="a2357-115">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a2357-115">MFCMAPI reference</span></span>

<span data-ttu-id="a2357-116">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a2357-116">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a2357-117">**文件**</span><span class="sxs-lookup"><span data-stu-id="a2357-117">**File**</span></span>|<span data-ttu-id="a2357-118">**函数**</span><span class="sxs-lookup"><span data-stu-id="a2357-118">**Function**</span></span>|<span data-ttu-id="a2357-119">**备注**</span><span class="sxs-lookup"><span data-stu-id="a2357-119">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2357-120">FormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="a2357-120">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="a2357-121">CFormContainerDlg:: OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="a2357-121">CFormContainerDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="a2357-122">MFCMAPI 使用**IMAPIFormContainer:: RemoveForm**方法从窗体容器中删除窗体。</span><span class="sxs-lookup"><span data-stu-id="a2357-122">MFCMAPI uses the **IMAPIFormContainer::RemoveForm** method to delete a form from a form container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a2357-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2357-123">See also</span></span>



[<span data-ttu-id="a2357-124">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a2357-124">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="a2357-125">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a2357-125">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

