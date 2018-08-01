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
ms.openlocfilehash: ec85f7bdfc9d2d275bdb5ffe7ba0113ad4a35c3b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775474"
---
# <a name="imapimessagesitesavemessage"></a><span data-ttu-id="d6290-103">IMAPIMessageSite::SaveMessage</span><span class="sxs-lookup"><span data-stu-id="d6290-103">IMAPIMessageSite::SaveMessage</span></span>

  
  
<span data-ttu-id="d6290-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d6290-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d6290-105">保存当前消息的请求。</span><span class="sxs-lookup"><span data-stu-id="d6290-105">Requests that the current message be saved.</span></span>
  
```cpp
HRESULT SaveMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="d6290-106">参数</span><span class="sxs-lookup"><span data-stu-id="d6290-106">Parameters</span></span>

<span data-ttu-id="d6290-107">无。</span><span class="sxs-lookup"><span data-stu-id="d6290-107">None.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d6290-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d6290-108">Return value</span></span>

<span data-ttu-id="d6290-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6290-109">S_OK</span></span> 
  
> <span data-ttu-id="d6290-110">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="d6290-110">The call succeeded and has returned the expected value or values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d6290-111">说明</span><span class="sxs-lookup"><span data-stu-id="d6290-111">Remarks</span></span>

<span data-ttu-id="d6290-112">窗体调用**IMAPIMessageSite::SaveMessage**方法以请求邮件被保存。</span><span class="sxs-lookup"><span data-stu-id="d6290-112">Forms call the **IMAPIMessageSite::SaveMessage** method to request that a message be saved.</span></span> 
  
<span data-ttu-id="d6290-113">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="d6290-113">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d6290-114">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="d6290-114">MFCMAPI reference</span></span>

<span data-ttu-id="d6290-115">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d6290-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d6290-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="d6290-116">**File**</span></span>|<span data-ttu-id="d6290-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="d6290-117">**Function**</span></span>|<span data-ttu-id="d6290-118">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d6290-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6290-119">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="d6290-119">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="d6290-120">CMyMAPIFormViewer::SaveMessage</span><span class="sxs-lookup"><span data-stu-id="d6290-120">CMyMAPIFormViewer::SaveMessage</span></span>  <br/> |<span data-ttu-id="d6290-121">MFCMAPI 使用**IMAPIMessageSite::SaveMessage**方法保存邮件。</span><span class="sxs-lookup"><span data-stu-id="d6290-121">MFCMAPI uses the **IMAPIMessageSite::SaveMessage** method to save the message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d6290-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6290-122">See also</span></span>



[<span data-ttu-id="d6290-123">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d6290-123">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="d6290-124">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d6290-124">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="d6290-125">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="d6290-125">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

