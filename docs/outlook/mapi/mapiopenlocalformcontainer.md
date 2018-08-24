---
title: MAPIOpenLocalFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenLocalFormContainer
api_type:
- COM
ms.assetid: 1c53170f-03a6-4a05-913e-de8eeadea692
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87696ceea96bd2f51bfe5a0b062499946179c8b3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582558"
---
# <a name="mapiopenlocalformcontainer"></a><span data-ttu-id="e6b91-103">MAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="e6b91-103">MAPIOpenLocalFormContainer</span></span>

  
  
<span data-ttu-id="e6b91-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6b91-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6b91-105">返回到本地表单库的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e6b91-105">Returns an interface pointer to the local form library.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6b91-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e6b91-106">Header file:</span></span>  <br/> |<span data-ttu-id="e6b91-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="e6b91-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="e6b91-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e6b91-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="e6b91-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="e6b91-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="e6b91-110">调用：</span><span class="sxs-lookup"><span data-stu-id="e6b91-110">Called by:</span></span>  <br/> |<span data-ttu-id="e6b91-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="e6b91-111">Client applications</span></span>  <br/> |
   
```cpp
MAPIOpenLocalFormContainer(
  LPMAPIFORMCONTAINER FAR * ppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="e6b91-112">参数</span><span class="sxs-lookup"><span data-stu-id="e6b91-112">Parameters</span></span>

 <span data-ttu-id="e6b91-113">_ppfcnt_</span><span class="sxs-lookup"><span data-stu-id="e6b91-113">_ppfcnt_</span></span>
  
> <span data-ttu-id="e6b91-114">[输出]指向本地窗体库接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e6b91-114">[out] Pointer to a pointer to the local form library interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e6b91-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e6b91-115">Return value</span></span>

<span data-ttu-id="e6b91-116">无。</span><span class="sxs-lookup"><span data-stu-id="e6b91-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e6b91-117">注解</span><span class="sxs-lookup"><span data-stu-id="e6b91-117">Remarks</span></span>

<span data-ttu-id="e6b91-118">第三方安装程序可以使用指针返回到该接口到库中安装应用程序特定的表单，而无需程序事先登录到 MAPI。</span><span class="sxs-lookup"><span data-stu-id="e6b91-118">The interface to which a pointer is returned can be used by third-party installation programs to install application-specific forms into the library without the program first having to log on to MAPI.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e6b91-119">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e6b91-119">MFCMAPI reference</span></span>

<span data-ttu-id="e6b91-120">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e6b91-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e6b91-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="e6b91-121">**File**</span></span>|<span data-ttu-id="e6b91-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="e6b91-122">**Function**</span></span>|<span data-ttu-id="e6b91-123">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e6b91-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6b91-124">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="e6b91-124">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="e6b91-125">CMainDlg::OnMAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="e6b91-125">CMainDlg::OnMAPIOpenLocalFormContainer</span></span>  <br/> |<span data-ttu-id="e6b91-126">MFCMAPI 使用**MAPIOpenLocalFormContainer**方法打开要在新窗口中呈现的本地窗体容器。</span><span class="sxs-lookup"><span data-stu-id="e6b91-126">MFCMAPI uses the **MAPIOpenLocalFormContainer** method to open the local form container to render in a new window.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e6b91-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b91-127">See also</span></span>



[<span data-ttu-id="e6b91-128">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e6b91-128">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

