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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c142424bb050ae287f54a87ea8a5e0ea45acb12c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351203"
---
# <a name="imapifoldersavecontentssort"></a><span data-ttu-id="e0cca-103">IMAPIFolder::SaveContentsSort</span><span class="sxs-lookup"><span data-stu-id="e0cca-103">IMAPIFolder::SaveContentsSort</span></span>

  
  
<span data-ttu-id="e0cca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0cca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0cca-105">设置文件夹的内容表的默认排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e0cca-105">Sets the default sort order for a folder's contents table.</span></span>
  
```cpp
HRESULT SaveContentsSort(
  LPSSortOrderSet lpSortCriteria,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e0cca-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0cca-106">Parameters</span></span>

 <span data-ttu-id="e0cca-107">_lpSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="e0cca-107">_lpSortCriteria_</span></span>
  
> <span data-ttu-id="e0cca-108">实时指向包含默认排序顺序的[SSortOrderSet](ssortorderset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e0cca-108">[in] A pointer to an [SSortOrderSet](ssortorderset.md) structure that contains the default sort order.</span></span> 
    
 <span data-ttu-id="e0cca-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e0cca-109">_ulFlags_</span></span>
  
> <span data-ttu-id="e0cca-110">实时用于控制如何设置默认排序顺序的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e0cca-110">[in] A bitmask of flags that controls how the default sort order is set.</span></span> <span data-ttu-id="e0cca-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="e0cca-111">The following flag can be set:</span></span>
    
<span data-ttu-id="e0cca-112">RECURSIVE_SORT</span><span class="sxs-lookup"><span data-stu-id="e0cca-112">RECURSIVE_SORT</span></span> 
  
> <span data-ttu-id="e0cca-113">默认的排序次序将应用于指定的文件夹及其所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e0cca-113">The default sort order set applies to the indicated folder and to all its subfolders.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e0cca-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e0cca-114">Return value</span></span>

<span data-ttu-id="e0cca-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0cca-115">S_OK</span></span> 
  
> <span data-ttu-id="e0cca-116">已成功保存排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e0cca-116">The sort order was successfully saved.</span></span>
    
<span data-ttu-id="e0cca-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e0cca-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="e0cca-118">邮件存储区提供程序不支持保存其文件夹内容表的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e0cca-118">The message store provider does not support saving a sort order for its folder contents tables.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e0cca-119">注解</span><span class="sxs-lookup"><span data-stu-id="e0cca-119">Remarks</span></span>

<span data-ttu-id="e0cca-120">**IMAPIFolder:: SaveContentsSort**方法为文件夹的内容表建立默认的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e0cca-120">The **IMAPIFolder::SaveContentsSort** method establishes a default sort order for a folder's contents table.</span></span> <span data-ttu-id="e0cca-121">也就是说, 当客户端在代码调用**SaveContentsSort**后调用文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法时, 返回的内容表中的行将按**SaveContentsSort**建立的顺序显示。</span><span class="sxs-lookup"><span data-stu-id="e0cca-121">That is, when a client calls the folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method after the code calls **SaveContentsSort**, the rows in the returned contents table will appear in the order established by **SaveContentsSort**.</span></span>
  
<span data-ttu-id="e0cca-122">并非所有邮件存储提供程序都支持**SaveContentsSort**;邮件存储提供程序从**SaveContentsSort**方法返回 MAPI_E_NO_SUPPORT 是可接受的。</span><span class="sxs-lookup"><span data-stu-id="e0cca-122">Not all message store providers support **SaveContentsSort**; it is acceptable for message store providers to return MAPI_E_NO_SUPPORT from the **SaveContentsSort** method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e0cca-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0cca-123">See also</span></span>



[<span data-ttu-id="e0cca-124">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="e0cca-124">IMAPIContainer::GetContentsTable</span></span>](imapicontainer-getcontentstable.md)
  
[<span data-ttu-id="e0cca-125">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="e0cca-125">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="e0cca-126">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e0cca-126">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)

