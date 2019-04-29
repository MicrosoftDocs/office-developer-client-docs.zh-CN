---
title: IMAPIMessageSiteSaveMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.SaveMessage
api_type:
- COM
ms.assetid: 94c44952-d297-4705-9778-90373dfa5ad6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 938eaa6c1a39d24157d5d690c42b435af6192cb6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417103"
---
# <a name="imapimessagesitesavemessage"></a><span data-ttu-id="5d4c8-103">IMAPIMessageSite::SaveMessage</span><span class="sxs-lookup"><span data-stu-id="5d4c8-103">IMAPIMessageSite::SaveMessage</span></span>

  
  
<span data-ttu-id="5d4c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d4c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d4c8-105">请求保存当前邮件。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-105">Requests that the current message be saved.</span></span>
  
```cpp
HRESULT SaveMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="5d4c8-106">参数</span><span class="sxs-lookup"><span data-stu-id="5d4c8-106">Parameters</span></span>

<span data-ttu-id="5d4c8-107">无。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-107">None.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="5d4c8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5d4c8-108">Return value</span></span>

<span data-ttu-id="5d4c8-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d4c8-109">S_OK</span></span> 
  
> <span data-ttu-id="5d4c8-110">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-110">The call succeeded and has returned the expected value or values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5d4c8-111">说明</span><span class="sxs-lookup"><span data-stu-id="5d4c8-111">Remarks</span></span>

<span data-ttu-id="5d4c8-112">表单调用**IMAPIMessageSite:: SaveMessage**方法以请求保存邮件。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-112">Forms call the **IMAPIMessageSite::SaveMessage** method to request that a message be saved.</span></span> 
  
<span data-ttu-id="5d4c8-113">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-113">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5d4c8-114">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="5d4c8-114">MFCMAPI reference</span></span>

<span data-ttu-id="5d4c8-115">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5d4c8-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="5d4c8-116">**File**</span></span>|<span data-ttu-id="5d4c8-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="5d4c8-117">**Function**</span></span>|<span data-ttu-id="5d4c8-118">**备注**</span><span class="sxs-lookup"><span data-stu-id="5d4c8-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d4c8-119">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="5d4c8-119">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="5d4c8-120">CMyMAPIFormViewer:: SaveMessage</span><span class="sxs-lookup"><span data-stu-id="5d4c8-120">CMyMAPIFormViewer::SaveMessage</span></span>  <br/> |<span data-ttu-id="5d4c8-121">MFCMAPI 使用**IMAPIMessageSite:: SaveMessage**方法保存邮件。</span><span class="sxs-lookup"><span data-stu-id="5d4c8-121">MFCMAPI uses the **IMAPIMessageSite::SaveMessage** method to save the message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5d4c8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4c8-122">See also</span></span>



[<span data-ttu-id="5d4c8-123">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5d4c8-123">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="5d4c8-124">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5d4c8-124">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="5d4c8-125">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="5d4c8-125">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

