---
title: MAPIOpenFormMgr
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenFormMgr
api_type:
- COM
ms.assetid: 5b624954-d975-4d5e-84d7-74e096ac30af
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de0c1181450c536dffd5a84242c17bd1dd612566
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418048"
---
# <a name="mapiopenformmgr"></a><span data-ttu-id="a4204-103">MAPIOpenFormMgr</span><span class="sxs-lookup"><span data-stu-id="a4204-103">MAPIOpenFormMgr</span></span>

  
  
<span data-ttu-id="a4204-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4204-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4204-105">打开现有会话上下文中的表单库提供程序对象上的 [IMAPIFormMgr](imapiformmgriunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="a4204-105">Opens an [IMAPIFormMgr](imapiformmgriunknown.md) interface on a form library provider object in the context of an existing session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4204-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a4204-106">Header file:</span></span>  <br/> |<span data-ttu-id="a4204-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="a4204-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="a4204-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a4204-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a4204-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a4204-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a4204-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a4204-110">Called by:</span></span>  <br/> |<span data-ttu-id="a4204-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a4204-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a><span data-ttu-id="a4204-112">参数</span><span class="sxs-lookup"><span data-stu-id="a4204-112">Parameters</span></span>

 <span data-ttu-id="a4204-113">_pSession_</span><span class="sxs-lookup"><span data-stu-id="a4204-113">_pSession_</span></span>
  
> <span data-ttu-id="a4204-114">[in]指向客户端应用程序使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="a4204-114">[in] Pointer to the session in use by the client application.</span></span>
    
 <span data-ttu-id="a4204-115">_ppmgr_</span><span class="sxs-lookup"><span data-stu-id="a4204-115">_ppmgr_</span></span>
  
> <span data-ttu-id="a4204-116">[out]指向返回的 **IMAPIFormMgr 接口的** 指针。</span><span class="sxs-lookup"><span data-stu-id="a4204-116">[out] Pointer to the returned **IMAPIFormMgr** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a4204-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a4204-117">Return value</span></span>

<span data-ttu-id="a4204-118">无。</span><span class="sxs-lookup"><span data-stu-id="a4204-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a4204-119">说明</span><span class="sxs-lookup"><span data-stu-id="a4204-119">Remarks</span></span>

<span data-ttu-id="a4204-120">在客户端应用程序调用 **MAPIOpenFormMgr** 函数后，大多数后续的表单相关交互都通过表单库提供程序或表单库提供程序返回的接口发生。</span><span class="sxs-lookup"><span data-stu-id="a4204-120">After a client application makes a call to the **MAPIOpenFormMgr** function, most subsequent forms-related interactions take place through the form library provider or an interface returned by the form library provider.</span></span> <span data-ttu-id="a4204-121">**IMAPIFormMgr** 接口允许客户端使用消息处理程序，并执行消息类和表单库之间的解决方案。</span><span class="sxs-lookup"><span data-stu-id="a4204-121">The **IMAPIFormMgr** interface allows the client to work with message handlers and perform resolutions between message classes and form libraries.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a4204-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a4204-122">MFCMAPI reference</span></span>

<span data-ttu-id="a4204-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a4204-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a4204-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="a4204-124">**File**</span></span>|<span data-ttu-id="a4204-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="a4204-125">**Function**</span></span>|<span data-ttu-id="a4204-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="a4204-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4204-127">MainDlg.cpp 打开表单管理器，以便选择表单。</span><span class="sxs-lookup"><span data-stu-id="a4204-127">MainDlg.cpp opens the form manager so a form can be selected.</span></span>  <br/> |<span data-ttu-id="a4204-128">CMainDlg：：OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="a4204-128">CMainDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="a4204-129">MFCMAPI 使用 **MAPIOpenFormMgr** 方法打开表单管理器，以便选择表单。</span><span class="sxs-lookup"><span data-stu-id="a4204-129">MFCMAPI uses the **MAPIOpenFormMgr** method to open the form manager so a form can be selected.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a4204-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4204-130">See also</span></span>



[<span data-ttu-id="a4204-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a4204-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

