---
title: IABContainerDeleteEntries
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.DeleteEntries
api_type:
- COM
ms.assetid: 70a24811-0c41-4b44-8c63-7ef807bc9051
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e3b238129e55e03da33ef3af75ecce7e73fbad03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425594"
---
# <a name="iabcontainerdeleteentries"></a><span data-ttu-id="84ec9-103">IABContainer::DeleteEntries</span><span class="sxs-lookup"><span data-stu-id="84ec9-103">IABContainer::DeleteEntries</span></span>

  
  
<span data-ttu-id="84ec9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84ec9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84ec9-105">删除一个或多个条目, 通常是邮件用户、通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="84ec9-105">Removes one or more entries, typically messaging users, distribution lists, or other containers.</span></span>
  
```cpp
HRESULT DeleteEntries(
  LPENTRYLIST lpEntries,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="84ec9-106">参数</span><span class="sxs-lookup"><span data-stu-id="84ec9-106">Parameters</span></span>

 <span data-ttu-id="84ec9-107">_lpEntries_</span><span class="sxs-lookup"><span data-stu-id="84ec9-107">_lpEntries_</span></span>
  
> <span data-ttu-id="84ec9-108">实时指向[ENTRYLIST](entrylist.md)结构数组的指针, 该数组包含表示要删除的项的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="84ec9-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that contain entry identifiers that represent the entries being deleted.</span></span> 
    
 <span data-ttu-id="84ec9-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="84ec9-109">_ulFlags_</span></span>
  
> <span data-ttu-id="84ec9-110">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="84ec9-110">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="84ec9-111">返回值</span><span class="sxs-lookup"><span data-stu-id="84ec9-111">Return value</span></span>

<span data-ttu-id="84ec9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="84ec9-112">S_OK</span></span> 
  
> <span data-ttu-id="84ec9-113">已成功删除指定的条目。</span><span class="sxs-lookup"><span data-stu-id="84ec9-113">The specified entries have been successfully deleted.</span></span> 
    
<span data-ttu-id="84ec9-114">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="84ec9-114">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="84ec9-115">调用成功, 但无法删除一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="84ec9-115">The call succeeded, but one or more of the entries could not be deleted.</span></span> <span data-ttu-id="84ec9-116">返回此值时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="84ec9-116">When this value is returned, the call should be handled as successful.</span></span> <span data-ttu-id="84ec9-117">若要测试此值, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="84ec9-117">To test for this value, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="84ec9-118">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="84ec9-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="84ec9-119">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="84ec9-119">MFCMAPI reference</span></span>

<span data-ttu-id="84ec9-120">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="84ec9-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="84ec9-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="84ec9-121">**File**</span></span>|<span data-ttu-id="84ec9-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="84ec9-122">**Function**</span></span>|<span data-ttu-id="84ec9-123">**备注**</span><span class="sxs-lookup"><span data-stu-id="84ec9-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84ec9-124">Abdlg</span><span class="sxs-lookup"><span data-stu-id="84ec9-124">Abdlg.cpp</span></span>  <br/> |<span data-ttu-id="84ec9-125">CabDlg:: OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="84ec9-125">CabDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="84ec9-126">MFCMAPI 使用**DeleteEntries**方法从通讯簿容器中删除特定的条目。</span><span class="sxs-lookup"><span data-stu-id="84ec9-126">MFCMAPI uses the **DeleteEntries** method to delete a specific entry from an address book container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="84ec9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84ec9-127">See also</span></span>



[<span data-ttu-id="84ec9-128">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="84ec9-128">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)


[<span data-ttu-id="84ec9-129">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="84ec9-129">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

