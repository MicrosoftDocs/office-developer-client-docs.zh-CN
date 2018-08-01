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
ms.openlocfilehash: 0d2c908f86ccd66ffd3a2eb2506d129ee2a14d48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775388"
---
# <a name="imapiformcontainerremoveform"></a><span data-ttu-id="94e2b-103">IMAPIFormContainer::RemoveForm</span><span class="sxs-lookup"><span data-stu-id="94e2b-103">IMAPIFormContainer::RemoveForm</span></span>

  
  
<span data-ttu-id="94e2b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="94e2b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="94e2b-105">从窗体容器中删除特定的窗体。</span><span class="sxs-lookup"><span data-stu-id="94e2b-105">Removes a particular form from a form container.</span></span>
  
```cpp
HRESULT RemoveForm(
  LPCSTR szMessageClass
);
```

## <a name="parameters"></a><span data-ttu-id="94e2b-106">参数</span><span class="sxs-lookup"><span data-stu-id="94e2b-106">Parameters</span></span>

 <span data-ttu-id="94e2b-107">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="94e2b-107">_szMessageClass_</span></span>
  
> <span data-ttu-id="94e2b-108">[in]命名窗体，从窗体容器中删除的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="94e2b-108">[in] A string that names the message class of the form to be removed from the form container.</span></span> <span data-ttu-id="94e2b-109">邮件类名称始终都是 ANSI 字符串，从不 Unicode。</span><span class="sxs-lookup"><span data-stu-id="94e2b-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="94e2b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="94e2b-110">Return value</span></span>

<span data-ttu-id="94e2b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="94e2b-111">S_OK</span></span> 
  
> <span data-ttu-id="94e2b-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="94e2b-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="94e2b-113">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="94e2b-113">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="94e2b-114">_SzMessageClass_参数中传递的邮件类不匹配窗体容器中的任何窗体的邮件类。</span><span class="sxs-lookup"><span data-stu-id="94e2b-114">The message class passed in the  _szMessageClass_ parameter does not match the message class of any form in the form container.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="94e2b-115">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="94e2b-115">MFCMAPI reference</span></span>

<span data-ttu-id="94e2b-116">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="94e2b-116">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="94e2b-117">**文件**</span><span class="sxs-lookup"><span data-stu-id="94e2b-117">**File**</span></span>|<span data-ttu-id="94e2b-118">**函数**</span><span class="sxs-lookup"><span data-stu-id="94e2b-118">**Function**</span></span>|<span data-ttu-id="94e2b-119">**Comment**</span><span class="sxs-lookup"><span data-stu-id="94e2b-119">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94e2b-120">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="94e2b-120">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="94e2b-121">CFormContainerDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="94e2b-121">CFormContainerDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="94e2b-122">MFCMAPI 使用**IMAPIFormContainer::RemoveForm**方法从窗体容器中删除窗体。</span><span class="sxs-lookup"><span data-stu-id="94e2b-122">MFCMAPI uses the **IMAPIFormContainer::RemoveForm** method to delete a form from a form container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="94e2b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94e2b-123">See also</span></span>



[<span data-ttu-id="94e2b-124">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="94e2b-124">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="94e2b-125">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="94e2b-125">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

