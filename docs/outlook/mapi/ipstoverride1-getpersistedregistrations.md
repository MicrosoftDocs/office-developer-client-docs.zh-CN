---
title: IPSTOVERRIDE1GetPersistedRegistrations
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1.GetPersistedRegistrations
api_type:
- COM
ms.assetid: 027092f0-f2d6-49e8-a8d0-8926824953a2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 822b4164737aa6010ccce108b544410104ac023d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415129"
---
# <a name="ipstoverride1getpersistedregistrations"></a><span data-ttu-id="b6c71-103">IPSTOVERRIDE1::GetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="b6c71-103">IPSTOVERRIDE1::GetPersistedRegistrations</span></span>

  
  
<span data-ttu-id="b6c71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6c71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6c71-105">检索个人文件夹的注册列表 (.pst) 文件。</span><span class="sxs-lookup"><span data-stu-id="b6c71-105">Retrieves the list of registrations for the Personal Folders (.pst) file.</span></span>
  
```cpp
HRESULT GetPersistedRegistration(SPropValue **ppmval);
```

## <a name="parameters"></a><span data-ttu-id="b6c71-106">参数</span><span class="sxs-lookup"><span data-stu-id="b6c71-106">Parameters</span></span>

 <span data-ttu-id="b6c71-107">_ppmval_</span><span class="sxs-lookup"><span data-stu-id="b6c71-107">_ppmval_</span></span>
  
> <span data-ttu-id="b6c71-108">[in]指向指向 [SPropValue 结构的指针的](spropvalue.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="b6c71-108">[in] A pointer to a pointer to an [SPropValue](spropvalue.md) structure.</span></span> <span data-ttu-id="b6c71-109">此结构的 ulPropTag 成员的类型为 PT_MV_UNICODE，MVszW 值成员将为以 null 终止的 Unicode 字符串数组。</span><span class="sxs-lookup"><span data-stu-id="b6c71-109">The ulPropTag member of this structure is of the type PT_MV_UNICODE, and the MVszW value member will be an array of null-terminated Unicode strings.</span></span> <span data-ttu-id="b6c71-110">这些字符串是一直保留注册的 DLL 的路径。</span><span class="sxs-lookup"><span data-stu-id="b6c71-110">These strings are paths to DLLs for which registration has been persisted.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b6c71-111">未实现对 ANSI 的 .pst 支持。</span><span class="sxs-lookup"><span data-stu-id="b6c71-111">.pst support for ANSI is not implemented.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="b6c71-112">返回值</span><span class="sxs-lookup"><span data-stu-id="b6c71-112">Return value</span></span>

<span data-ttu-id="b6c71-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6c71-113">S_OK</span></span> 
  
> <span data-ttu-id="b6c71-114">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="b6c71-114">The function call was successful.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6c71-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6c71-115">See also</span></span>



[<span data-ttu-id="b6c71-116">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6c71-116">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md)
  
[<span data-ttu-id="b6c71-117">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6c71-117">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

