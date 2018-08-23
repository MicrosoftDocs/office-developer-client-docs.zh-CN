---
title: IMAPIMessageSiteGetFormManager
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetFormManager
api_type:
- COM
ms.assetid: d48bd537-c562-4deb-8a4c-011208991054
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e3a2224daace9be7f4504a693806ccb3cf4abbe
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570490"
---
# <a name="imapimessagesitegetformmanager"></a><span data-ttu-id="ee482-103">IMAPIMessageSite::GetFormManager</span><span class="sxs-lookup"><span data-stu-id="ee482-103">IMAPIMessageSite::GetFormManager</span></span>

  
  
<span data-ttu-id="ee482-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee482-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee482-105">返回一个窗体管理器接口，窗体服务器可用于打开窗体的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="ee482-105">Returns a form manager interface, which a form server can use to open another form server.</span></span>
  
```cpp
HRESULT GetFormManager(
  LPMAPIFORMMGR FAR * ppFormMgr
);
```

## <a name="parameters"></a><span data-ttu-id="ee482-106">参数</span><span class="sxs-lookup"><span data-stu-id="ee482-106">Parameters</span></span>

 <span data-ttu-id="ee482-107">_ppFormMgr_</span><span class="sxs-lookup"><span data-stu-id="ee482-107">_ppFormMgr_</span></span>
  
> <span data-ttu-id="ee482-108">[输出]指向返回窗体管理器接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ee482-108">[out] A pointer to a pointer to the returned form manager interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ee482-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ee482-109">Return value</span></span>

<span data-ttu-id="ee482-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee482-110">S_OK</span></span> 
  
> <span data-ttu-id="ee482-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="ee482-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ee482-112">注解</span><span class="sxs-lookup"><span data-stu-id="ee482-112">Remarks</span></span>

<span data-ttu-id="ee482-113">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="ee482-113">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ee482-114">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ee482-114">MFCMAPI reference</span></span>

<span data-ttu-id="ee482-115">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ee482-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ee482-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="ee482-116">**File**</span></span>|<span data-ttu-id="ee482-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="ee482-117">**Function**</span></span>|<span data-ttu-id="ee482-118">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ee482-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee482-119">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="ee482-119">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="ee482-120">CMyMAPIFormViewer::GetFormManager</span><span class="sxs-lookup"><span data-stu-id="ee482-120">CMyMAPIFormViewer::GetFormManager</span></span>  <br/> |<span data-ttu-id="ee482-121">MFCMAPI 使用**IMAPIMessageSite::GetFormManager**方法调用[MAPIOpenFormMgr](mapiopenformmgr.md)并返回该调用的结果。</span><span class="sxs-lookup"><span data-stu-id="ee482-121">MFCMAPI uses the **IMAPIMessageSite::GetFormManager** method to call [MAPIOpenFormMgr](mapiopenformmgr.md) and return the results of that call.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ee482-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee482-122">See also</span></span>



[<span data-ttu-id="ee482-123">MAPIOpenFormMgr</span><span class="sxs-lookup"><span data-stu-id="ee482-123">MAPIOpenFormMgr</span></span>](mapiopenformmgr.md)
  
[<span data-ttu-id="ee482-124">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ee482-124">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="ee482-125">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ee482-125">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="ee482-126">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="ee482-126">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

