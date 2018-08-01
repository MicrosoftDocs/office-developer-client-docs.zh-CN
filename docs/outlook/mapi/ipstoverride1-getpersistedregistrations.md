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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 56aaf5caf93f90f54d152ab3684ca592cd45cd1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776032"
---
# <a name="ipstoverride1getpersistedregistrations"></a><span data-ttu-id="d2aaf-103">IPSTOVERRIDE1::GetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="d2aaf-103">IPSTOVERRIDE1::GetPersistedRegistrations</span></span>

  
  
<span data-ttu-id="d2aaf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d2aaf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d2aaf-105">检索的登记个人文件夹 (.pst) 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-105">Retrieves the list of registrations for the Personal Folders (.pst) file.</span></span>
  
```cpp
HRESULT GetPersistedRegistration(SPropValue **ppmval);
```

## <a name="parameters"></a><span data-ttu-id="d2aaf-106">参数</span><span class="sxs-lookup"><span data-stu-id="d2aaf-106">Parameters</span></span>

 <span data-ttu-id="d2aaf-107">_ppmval_</span><span class="sxs-lookup"><span data-stu-id="d2aaf-107">_ppmval_</span></span>
  
> <span data-ttu-id="d2aaf-108">[in]指向[SPropValue](spropvalue.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-108">[in] A pointer to a pointer to an [SPropValue](spropvalue.md) structure.</span></span> <span data-ttu-id="d2aaf-109">此结构的 ulPropTag 成员的类型 PT_MV_UNICODE，并且 MVszW 值成员都是 null 结尾的 Unicode 字符串数组。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-109">The ulPropTag member of this structure is of the type PT_MV_UNICODE, and the MVszW value member will be an array of null-terminated Unicode strings.</span></span> <span data-ttu-id="d2aaf-110">这些字符串是对已经为其保持了注册的 Dll 的路径。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-110">These strings are paths to DLLs for which registration has been persisted.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d2aaf-111">未实现 ANSI.pst 支持。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-111">.pst support for ANSI is not implemented.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="d2aaf-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d2aaf-112">Return value</span></span>

<span data-ttu-id="d2aaf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2aaf-113">S_OK</span></span> 
  
> <span data-ttu-id="d2aaf-114">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d2aaf-114">The function call was successful.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d2aaf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2aaf-115">See also</span></span>



[<span data-ttu-id="d2aaf-116">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d2aaf-116">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md)
  
[<span data-ttu-id="d2aaf-117">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d2aaf-117">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

