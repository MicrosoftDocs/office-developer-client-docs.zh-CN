---
title: IAddrBookSetSearchPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetSearchPath
api_type:
- COM
ms.assetid: fbff82de-77d3-411e-a30c-a37cefdd92fc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4f9d2f4d271e467d8fac32b8f17faa8f66cd3f99
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775264"
---
# <a name="iaddrbooksetsearchpath"></a><span data-ttu-id="59052-103">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="59052-103">IAddrBook::SetSearchPath</span></span>

  
  
<span data-ttu-id="59052-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="59052-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59052-105">设置中的配置文件的名称解析过程使用新的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="59052-105">Sets a new search path in the profile that is used for the name resolution process.</span></span> 
  
```cpp
HRESULT SetSearchPath(
  ULONG ulFlags,
  LPSRowSet lpSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="59052-106">参数</span><span class="sxs-lookup"><span data-stu-id="59052-106">Parameters</span></span>

 <span data-ttu-id="59052-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="59052-107">_ulFlags_</span></span>
  
> <span data-ttu-id="59052-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="59052-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="59052-109">_lpSearchPath_</span><span class="sxs-lookup"><span data-stu-id="59052-109">_lpSearchPath_</span></span>
  
> <span data-ttu-id="59052-110">[in]指向用于保留搜索路径[SRowSet](srowset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="59052-110">[in] A pointer to the [SRowSet](srowset.md) structure used to hold the search path.</span></span> <span data-ttu-id="59052-111">对于每个**aRow**成员**SRowSet**中的第一个属性必须**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="59052-111">The first property for each **aRow** member in **SRowSet** must be **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="59052-112">返回值</span><span class="sxs-lookup"><span data-stu-id="59052-112">Return value</span></span>

<span data-ttu-id="59052-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="59052-113">S_OK</span></span> 
  
> <span data-ttu-id="59052-114">已成功设置的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="59052-114">The search path was successfully set.</span></span>
    
<span data-ttu-id="59052-115">MAPI_E_MISSING_REQUIRED_COLUMN</span><span class="sxs-lookup"><span data-stu-id="59052-115">MAPI_E_MISSING_REQUIRED_COLUMN</span></span> 
  
> <span data-ttu-id="59052-116">一个**SRowSet**结构中所述的容器不包括其**PR_ENTRYID**属性。</span><span class="sxs-lookup"><span data-stu-id="59052-116">One of the containers described in the **SRowSet** structure did not include its **PR_ENTRYID** property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="59052-117">备注</span><span class="sxs-lookup"><span data-stu-id="59052-117">Remarks</span></span>

<span data-ttu-id="59052-118">客户端和服务提供商调用**SetSearchPath**方法以保存所做的用于将名称解析使用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法的容器搜索顺序的更改。</span><span class="sxs-lookup"><span data-stu-id="59052-118">Clients and service providers call the **SetSearchPath** method to save changes that were made to the container search order that is used to resolve names with the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="59052-119">会话的实例之间保存搜索路径。</span><span class="sxs-lookup"><span data-stu-id="59052-119">The search path is saved between instances of a session.</span></span> 
  
<span data-ttu-id="59052-120">客户端和提供程序不需要调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法进行永久搜索路径更改。</span><span class="sxs-lookup"><span data-stu-id="59052-120">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the search path changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="59052-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59052-121">See also</span></span>



[<span data-ttu-id="59052-122">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="59052-122">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="59052-123">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="59052-123">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="59052-124">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="59052-124">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="59052-125">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="59052-125">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="59052-126">IAddrBook: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="59052-126">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

