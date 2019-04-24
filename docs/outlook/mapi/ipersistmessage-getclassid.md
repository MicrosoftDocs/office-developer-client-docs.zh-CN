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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f0d98b8ffa13fe238fc0fcf8ff0ec76a3a284eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309623"
---
# <a name="ipersistmessagegetclassid"></a><span data-ttu-id="d509a-103">IPersistMessage::GetClassID</span><span class="sxs-lookup"><span data-stu-id="d509a-103">IPersistMessage::GetClassID</span></span>

  
  
<span data-ttu-id="d509a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d509a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d509a-105">返回一个标识符, 表示可以管理窗体的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="d509a-105">Returns an identifier that represents the form server that can manage the form.</span></span> 
  
```cpp
HRESULT GetClassID(
  LPCLSID lpClassID
);
```

## <a name="parameters"></a><span data-ttu-id="d509a-106">参数</span><span class="sxs-lookup"><span data-stu-id="d509a-106">Parameters</span></span>

 <span data-ttu-id="d509a-107">_lpClassID_</span><span class="sxs-lookup"><span data-stu-id="d509a-107">_lpClassID_</span></span>
  
> <span data-ttu-id="d509a-108">[in, out]指向表单的类标识符 (CLSID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="d509a-108">[in, out] A pointer to the class identifier (CLSID) of the form.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d509a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d509a-109">Return value</span></span>

<span data-ttu-id="d509a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d509a-110">S_OK</span></span> 
  
> <span data-ttu-id="d509a-111">已成功返回类标识符。</span><span class="sxs-lookup"><span data-stu-id="d509a-111">The class identifier was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d509a-112">注解</span><span class="sxs-lookup"><span data-stu-id="d509a-112">Remarks</span></span>

<span data-ttu-id="d509a-113">**IPersistMessge:: GetClassID**方法将_lpClassID_参数的内容设置为窗体服务器的类标识符, 并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d509a-113">The **IPersistMessge::GetClassID** method sets the contents of the  _lpClassID_ parameter to the form server's class identifier and returns S_OK.</span></span> <span data-ttu-id="d509a-114">当表单查看器调用**GetClassID**并成功返回时, 窗体将置于[未初始化](uninitialized-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="d509a-114">When a form viewer calls **GetClassID** and it returns successfully, the form is placed in the [Uninitialized](uninitialized-state.md) state.</span></span> 
  
<span data-ttu-id="d509a-115">有关如何将类标识符与结构化存储对象结合使用的详细信息, 请参阅[IPersist:: GetClassID](https://msdn.microsoft.com/library/921a3b86-a240-454e-9411-8d653e02b90e.aspx)方法的相关文档。</span><span class="sxs-lookup"><span data-stu-id="d509a-115">For more information about how class identifiers are used with structured storage objects, see the documentation for the [IPersist::GetClassID](https://msdn.microsoft.com/library/921a3b86-a240-454e-9411-8d653e02b90e.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d509a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d509a-116">See also</span></span>



[<span data-ttu-id="d509a-117">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d509a-117">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

