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
ms.openlocfilehash: 592bd2c88c8eea17d80fe7cb725b075235c51763
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776374"
---
# <a name="mapiopenformmgr"></a><span data-ttu-id="9bf41-103">MAPIOpenFormMgr</span><span class="sxs-lookup"><span data-stu-id="9bf41-103">MAPIOpenFormMgr</span></span>

  
  
<span data-ttu-id="9bf41-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9bf41-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9bf41-105">现有会话的上下文中打开窗体库提供程序对象上的[IMAPIFormMgr](imapiformmgriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9bf41-105">Opens an [IMAPIFormMgr](imapiformmgriunknown.md) interface on a form library provider object in the context of an existing session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9bf41-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9bf41-106">Header file:</span></span>  <br/> |<span data-ttu-id="9bf41-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="9bf41-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="9bf41-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="9bf41-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9bf41-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9bf41-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9bf41-110">调用：</span><span class="sxs-lookup"><span data-stu-id="9bf41-110">Called by:</span></span>  <br/> |<span data-ttu-id="9bf41-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="9bf41-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a><span data-ttu-id="9bf41-112">参数</span><span class="sxs-lookup"><span data-stu-id="9bf41-112">Parameters</span></span>

 <span data-ttu-id="9bf41-113">_pSession_</span><span class="sxs-lookup"><span data-stu-id="9bf41-113">_pSession_</span></span>
  
> <span data-ttu-id="9bf41-114">[in]加入会话，使用客户端应用程序的指针。</span><span class="sxs-lookup"><span data-stu-id="9bf41-114">[in] Pointer to the session in use by the client application.</span></span>
    
 <span data-ttu-id="9bf41-115">_ppmgr_</span><span class="sxs-lookup"><span data-stu-id="9bf41-115">_ppmgr_</span></span>
  
> <span data-ttu-id="9bf41-116">[输出]对返回**IMAPIFormMgr**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="9bf41-116">[out] Pointer to the returned **IMAPIFormMgr** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9bf41-117">返回值</span><span class="sxs-lookup"><span data-stu-id="9bf41-117">Return value</span></span>

<span data-ttu-id="9bf41-118">无。</span><span class="sxs-lookup"><span data-stu-id="9bf41-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9bf41-119">说明</span><span class="sxs-lookup"><span data-stu-id="9bf41-119">Remarks</span></span>

<span data-ttu-id="9bf41-120">客户端应用程序，可以对**MAPIOpenFormMgr**函数的调用之后，大多数后续窗体相关进行交互通过表单库提供程序或表单库提供程序返回的接口。</span><span class="sxs-lookup"><span data-stu-id="9bf41-120">After a client application makes a call to the **MAPIOpenFormMgr** function, most subsequent forms-related interactions take place through the form library provider or an interface returned by the form library provider.</span></span> <span data-ttu-id="9bf41-121">**IMAPIFormMgr**界面允许客户端使用消息处理程序，并执行邮件类和窗体库之间的分辨率。</span><span class="sxs-lookup"><span data-stu-id="9bf41-121">The **IMAPIFormMgr** interface allows the client to work with message handlers and perform resolutions between message classes and form libraries.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9bf41-122">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9bf41-122">MFCMAPI reference</span></span>

<span data-ttu-id="9bf41-123">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9bf41-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9bf41-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="9bf41-124">**File**</span></span>|<span data-ttu-id="9bf41-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="9bf41-125">**Function**</span></span>|<span data-ttu-id="9bf41-126">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9bf41-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9bf41-127">MainDlg.cpp 打开窗体管理器，以便可以选择窗体。</span><span class="sxs-lookup"><span data-stu-id="9bf41-127">MainDlg.cpp opens the form manager so a form can be selected.</span></span>  <br/> |<span data-ttu-id="9bf41-128">CMainDlg::OnSelectForm</span><span class="sxs-lookup"><span data-stu-id="9bf41-128">CMainDlg::OnSelectForm</span></span>  <br/> |<span data-ttu-id="9bf41-129">MFCMAPI 使用**MAPIOpenFormMgr**方法打开窗体管理器，因此可以选择窗体。</span><span class="sxs-lookup"><span data-stu-id="9bf41-129">MFCMAPI uses the **MAPIOpenFormMgr** method to open the form manager so a form can be selected.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9bf41-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf41-130">See also</span></span>



[<span data-ttu-id="9bf41-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9bf41-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

