---
title: IMAPIFolderSaveContentsSort
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SaveContentsSort
api_type:
- COM
ms.assetid: 5ae3fdf0-6193-4c1f-bd2e-d69c56d69773
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1f79265c4356747e64aa8102dd4486db229baf5a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579660"
---
# <a name="imapifoldersavecontentssort"></a><span data-ttu-id="9abb8-103">IMAPIFolder::SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="9abb8-103">IMAPIFolder::SaveContentsSort</span></span>

  
  
<span data-ttu-id="9abb8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9abb8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9abb8-105">设置某个文件夹的内容表的默认排序次序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-105">Sets the default sort order for a folder's contents table.</span></span>
  
```cpp
HRESULT SaveContentsSort(
  LPSSortOrderSet lpSortCriteria,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9abb8-106">参数</span><span class="sxs-lookup"><span data-stu-id="9abb8-106">Parameters</span></span>

 <span data-ttu-id="9abb8-107">_lpSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="9abb8-107">_lpSortCriteria_</span></span>
  
> <span data-ttu-id="9abb8-108">[in]一个指向[SSortOrderSet](ssortorderset.md)结构，其中包含的默认排序次序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-108">[in] A pointer to an [SSortOrderSet](ssortorderset.md) structure that contains the default sort order.</span></span> 
    
 <span data-ttu-id="9abb8-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9abb8-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9abb8-110">[in]设置控制默认排序顺序的方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="9abb8-110">[in] A bitmask of flags that controls how the default sort order is set.</span></span> <span data-ttu-id="9abb8-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="9abb8-111">The following flag can be set:</span></span>
    
<span data-ttu-id="9abb8-112">RECURSIVE_SORT</span><span class="sxs-lookup"><span data-stu-id="9abb8-112">RECURSIVE_SORT</span></span> 
  
> <span data-ttu-id="9abb8-113">设置的默认排序顺序适用于指示的文件夹和所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9abb8-113">The default sort order set applies to the indicated folder and to all its subfolders.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9abb8-114">返回值</span><span class="sxs-lookup"><span data-stu-id="9abb8-114">Return value</span></span>

<span data-ttu-id="9abb8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9abb8-115">S_OK</span></span> 
  
> <span data-ttu-id="9abb8-116">已成功保存的排序次序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-116">The sort order was successfully saved.</span></span>
    
<span data-ttu-id="9abb8-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="9abb8-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="9abb8-118">消息存储提供程序不支持保存其文件夹内容表的排序次序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-118">The message store provider does not support saving a sort order for its folder contents tables.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9abb8-119">注解</span><span class="sxs-lookup"><span data-stu-id="9abb8-119">Remarks</span></span>

<span data-ttu-id="9abb8-120">**IMAPIFolder::SaveContentsSort**方法可创建一个文件夹内容表的默认排序次序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-120">The **IMAPIFolder::SaveContentsSort** method establishes a default sort order for a folder's contents table.</span></span> <span data-ttu-id="9abb8-121">即，当客户端代码调用**SaveContentsSort**后调用该文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法，将建立**SaveContentsSort**顺序出现返回的内容表中的行。</span><span class="sxs-lookup"><span data-stu-id="9abb8-121">That is, when a client calls the folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method after the code calls **SaveContentsSort**, the rows in the returned contents table will appear in the order established by **SaveContentsSort**.</span></span>
  
<span data-ttu-id="9abb8-122">并非所有的消息存储提供程序支持**SaveContentsSort**;它是适用于从**SaveContentsSort**方法返回 MAPI_E_NO_SUPPORT 的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="9abb8-122">Not all message store providers support **SaveContentsSort**; it is acceptable for message store providers to return MAPI_E_NO_SUPPORT from the **SaveContentsSort** method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9abb8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9abb8-123">See also</span></span>



[<span data-ttu-id="9abb8-124">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="9abb8-124">IMAPIContainer::GetContentsTable</span></span>](imapicontainer-getcontentstable.md)
  
[<span data-ttu-id="9abb8-125">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="9abb8-125">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="9abb8-126">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="9abb8-126">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

