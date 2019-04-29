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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8611249207811446ae47f056486ec498bf1e7eab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426203"
---
# <a name="iaddrbooksetsearchpath"></a><span data-ttu-id="b8406-103">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="b8406-103">IAddrBook::SetSearchPath</span></span>

  
  
<span data-ttu-id="b8406-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b8406-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b8406-105">在用于名称解析过程的配置文件中设置新的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="b8406-105">Sets a new search path in the profile that is used for the name resolution process.</span></span> 
  
```cpp
HRESULT SetSearchPath(
  ULONG ulFlags,
  LPSRowSet lpSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="b8406-106">参数</span><span class="sxs-lookup"><span data-stu-id="b8406-106">Parameters</span></span>

 <span data-ttu-id="b8406-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b8406-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b8406-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="b8406-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b8406-109">_lpSearchPath_</span><span class="sxs-lookup"><span data-stu-id="b8406-109">_lpSearchPath_</span></span>
  
> <span data-ttu-id="b8406-110">实时指向用于保存搜索路径的[SRowSet](srowset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b8406-110">[in] A pointer to the [SRowSet](srowset.md) structure used to hold the search path.</span></span> <span data-ttu-id="b8406-111">**SRowSet**中每个**aRow**成员的第一个属性必须为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="b8406-111">The first property for each **aRow** member in **SRowSet** must be **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b8406-112">返回值</span><span class="sxs-lookup"><span data-stu-id="b8406-112">Return value</span></span>

<span data-ttu-id="b8406-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8406-113">S_OK</span></span> 
  
> <span data-ttu-id="b8406-114">成功设置了搜索路径。</span><span class="sxs-lookup"><span data-stu-id="b8406-114">The search path was successfully set.</span></span>
    
<span data-ttu-id="b8406-115">MAPI_E_MISSING_REQUIRED_COLUMN</span><span class="sxs-lookup"><span data-stu-id="b8406-115">MAPI_E_MISSING_REQUIRED_COLUMN</span></span> 
  
> <span data-ttu-id="b8406-116">**SRowSet**结构中所述的一个容器不包含其**PR_ENTRYID**属性。</span><span class="sxs-lookup"><span data-stu-id="b8406-116">One of the containers described in the **SRowSet** structure did not include its **PR_ENTRYID** property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b8406-117">说明</span><span class="sxs-lookup"><span data-stu-id="b8406-117">Remarks</span></span>

<span data-ttu-id="b8406-118">客户端和服务提供程序调用**SetSearchPath**方法, 以保存对用于使用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法解析名称的容器搜索顺序所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b8406-118">Clients and service providers call the **SetSearchPath** method to save changes that were made to the container search order that is used to resolve names with the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="b8406-119">在会话实例之间保存搜索路径。</span><span class="sxs-lookup"><span data-stu-id="b8406-119">The search path is saved between instances of a session.</span></span> 
  
<span data-ttu-id="b8406-120">客户端和提供程序无需调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以使搜索路径更改永久。</span><span class="sxs-lookup"><span data-stu-id="b8406-120">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the search path changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b8406-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8406-121">See also</span></span>



[<span data-ttu-id="b8406-122">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="b8406-122">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="b8406-123">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="b8406-123">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="b8406-124">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="b8406-124">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="b8406-125">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="b8406-125">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="b8406-126">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b8406-126">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

