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
# <a name="mapiopenformmgr"></a><span data-ttu-id="49fb3-103">MAPIOpenFormMgr</span><span class="sxs-lookup"><span data-stu-id="49fb3-103">MAPIOpenFormMgr</span></span>

  
  
<span data-ttu-id="49fb3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49fb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49fb3-105">在现有会话的上下文中打开表单库提供程序对象上的[IMAPIFormMgr](imapiformmgriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="49fb3-105">Opens an [IMAPIFormMgr](imapiformmgriunknown.md) interface on a form library provider object in the context of an existing session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="49fb3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="49fb3-106">Header file:</span></span>  <br/> |<span data-ttu-id="49fb3-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="49fb3-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="49fb3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="49fb3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="49fb3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="49fb3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="49fb3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="49fb3-110">Called by:</span></span>  <br/> |<span data-ttu-id="49fb3-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="49fb3-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a><span data-ttu-id="49fb3-112">参数</span><span class="sxs-lookup"><span data-stu-id="49fb3-112">Parameters</span></span>

 <span data-ttu-id="49fb3-113">_pSession_</span><span class="sxs-lookup"><span data-stu-id="49fb3-113">_pSession_</span></span>
  
> <span data-ttu-id="49fb3-114">实时指向客户端应用程序正在使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="49fb3-114">[in] Pointer to the session in use by the client application.</span></span>
    
 <span data-ttu-id="49fb3-115">_ppmgr_</span><span class="sxs-lookup"><span data-stu-id="49fb3-115">_ppmgr_</span></span>
  
> <span data-ttu-id="49fb3-116">排除指向返回的**IMAPIFormMgr**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="49fb3-116">[out] Pointer to the returned **IMAPIFormMgr** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="49fb3-117">返回值</span><span class="sxs-lookup"><span data-stu-id="49fb3-117">Return value</span></span>

<span data-ttu-id="49fb3-118">无。</span><span class="sxs-lookup"><span data-stu-id="49fb3-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="49fb3-119">说明</span><span class="sxs-lookup"><span data-stu-id="49fb3-119">Remarks</span></span>

<span data-ttu-id="49fb3-120">在客户端应用程序调用**MAPIOpenFormMgr**函数之后, 大多数随后与表单相关的交互通过表单库提供程序或由表单库提供程序返回的接口进行。</span><span class="sxs-lookup"><span data-stu-id="49fb3-120">After a client application makes a call to the **MAPIOpenFormMgr** function, most subsequent forms-related interactions take place through the form library provider or an interface returned by the form library provider.</span></span> <span data-ttu-id="49fb3-121">**IMAPIFormMgr**接口允许客户端处理邮件处理程序, 并在邮件类别和表单库之间执行解析。</span><span class="sxs-lookup"><span data-stu-id="49fb3-121">The **IMAPIFormMgr** interface allows the client to work with message handlers and perform resolutions between message classes and form libraries.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="49fb3-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="49fb3-122">MFCMAPI reference</span></span>

<span data-ttu-id="49fb3-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="49fb3-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="49fb3-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="49fb3-124">**File**</span></span>|<span data-ttu-id="49fb3-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="49fb3-125">**Function**</span></span>|<span data-ttu-id="49fb3-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="49fb3-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="49fb3-127">MainDlg 打开窗体管理器, 以便可以选择窗体。</span><span class="sxs-lookup"><span data-stu-id="49fb3-127">MainDlg.cpp opens the form manager so a form can be selected.</span></span>  <br/> |<span data-ttu-id="49fb3-128">CMainDlg:: OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="49fb3-128">CMainDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="49fb3-129">MFCMAPI 使用**MAPIOpenFormMgr**方法打开表单管理器, 以便可以选择表单。</span><span class="sxs-lookup"><span data-stu-id="49fb3-129">MFCMAPI uses the **MAPIOpenFormMgr** method to open the form manager so a form can be selected.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="49fb3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49fb3-130">See also</span></span>



[<span data-ttu-id="49fb3-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="49fb3-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

