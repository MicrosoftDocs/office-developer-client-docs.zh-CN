---
title: IPersistMessageGetClassID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.GetClassID
api_type:
- COM
ms.assetid: 77eeb468-3432-4ccd-9c1e-1df9ce605193
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e0937eed2e8ca61bc18ee45ff20337267808ea70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775978"
---
# <a name="ipersistmessagegetclassid"></a><span data-ttu-id="dd9b9-103">IPersistMessage::GetClassID</span><span class="sxs-lookup"><span data-stu-id="dd9b9-103">IPersistMessage::GetClassID</span></span>

  
  
<span data-ttu-id="dd9b9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dd9b9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dd9b9-105">返回表示可以管理窗体的窗体服务器的标识符。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-105">Returns an identifier that represents the form server that can manage the form.</span></span> 
  
```cpp
HRESULT GetClassID(
  LPCLSID lpClassID
);
```

## <a name="parameters"></a><span data-ttu-id="dd9b9-106">参数</span><span class="sxs-lookup"><span data-stu-id="dd9b9-106">Parameters</span></span>

 <span data-ttu-id="dd9b9-107">_lpClassID_</span><span class="sxs-lookup"><span data-stu-id="dd9b9-107">_lpClassID_</span></span>
  
> <span data-ttu-id="dd9b9-108">[传入、 传出]指向该窗体的类标识符 (CLSID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-108">[in, out] A pointer to the class identifier (CLSID) of the form.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dd9b9-109">返回值</span><span class="sxs-lookup"><span data-stu-id="dd9b9-109">Return value</span></span>

<span data-ttu-id="dd9b9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd9b9-110">S_OK</span></span> 
  
> <span data-ttu-id="dd9b9-111">已成功返回的类标识符。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-111">The class identifier was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dd9b9-112">说明</span><span class="sxs-lookup"><span data-stu-id="dd9b9-112">Remarks</span></span>

<span data-ttu-id="dd9b9-113">**IPersistMessge::GetClassID**方法设置为窗体服务器的类标识符的_lpClassID_参数的内容，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-113">The **IPersistMessge::GetClassID** method sets the contents of the  _lpClassID_ parameter to the form server's class identifier and returns S_OK.</span></span> <span data-ttu-id="dd9b9-114">当窗体查看器调用**GetClassID**和它成功返回时，窗体处于[未初始化](uninitialized-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-114">When a form viewer calls **GetClassID** and it returns successfully, the form is placed in the [Uninitialized](uninitialized-state.md) state.</span></span> 
  
<span data-ttu-id="dd9b9-115">有关如何使用结构化的存储对象使用的类标识符的详细信息，请参阅[IPersist::GetClassID](http://msdn.microsoft.com/library/921a3b86-a240-454e-9411-8d653e02b90e.aspx)方法的文档。</span><span class="sxs-lookup"><span data-stu-id="dd9b9-115">For more information about how class identifiers are used with structured storage objects, see the documentation for the [IPersist::GetClassID](http://msdn.microsoft.com/library/921a3b86-a240-454e-9411-8d653e02b90e.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dd9b9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd9b9-116">See also</span></span>



[<span data-ttu-id="dd9b9-117">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dd9b9-117">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

