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
ms.openlocfilehash: 4140dc39b7f866b0372e5940aef5efc0524ad593
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573108"
---
# <a name="iabcontainerdeleteentries"></a><span data-ttu-id="c7a4e-103">IABContainer::DeleteEntries</span><span class="sxs-lookup"><span data-stu-id="c7a4e-103">IABContainer::DeleteEntries</span></span>

  
  
<span data-ttu-id="c7a4e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7a4e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7a4e-105">删除一个或多个条目，通常消息的用户、 通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-105">Removes one or more entries, typically messaging users, distribution lists, or other containers.</span></span>
  
```cpp
HRESULT DeleteEntries(
  LPENTRYLIST lpEntries,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c7a4e-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7a4e-106">Parameters</span></span>

 <span data-ttu-id="c7a4e-107">_lpEntries_</span><span class="sxs-lookup"><span data-stu-id="c7a4e-107">_lpEntries_</span></span>
  
> <span data-ttu-id="c7a4e-108">[in]一个指向包含代表要删除的条目的项标识符的[ENTRYLIST](entrylist.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that contain entry identifiers that represent the entries being deleted.</span></span> 
    
 <span data-ttu-id="c7a4e-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c7a4e-109">_ulFlags_</span></span>
  
> <span data-ttu-id="c7a4e-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-110">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c7a4e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c7a4e-111">Return value</span></span>

<span data-ttu-id="c7a4e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7a4e-112">S_OK</span></span> 
  
> <span data-ttu-id="c7a4e-113">已成功删除指定的项。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-113">The specified entries have been successfully deleted.</span></span> 
    
<span data-ttu-id="c7a4e-114">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="c7a4e-114">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="c7a4e-115">调用成功，但无法删除一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-115">The call succeeded, but one or more of the entries could not be deleted.</span></span> <span data-ttu-id="c7a4e-116">返回此值时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-116">When this value is returned, the call should be handled as successful.</span></span> <span data-ttu-id="c7a4e-117">若要测试此值，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-117">To test for this value, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="c7a4e-118">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="c7a4e-119">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c7a4e-119">MFCMAPI reference</span></span>

<span data-ttu-id="c7a4e-120">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c7a4e-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="c7a4e-121">**File**</span></span>|<span data-ttu-id="c7a4e-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="c7a4e-122">**Function**</span></span>|<span data-ttu-id="c7a4e-123">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c7a4e-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7a4e-124">Abdlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c7a4e-124">Abdlg.cpp</span></span>  <br/> |<span data-ttu-id="c7a4e-125">CabDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="c7a4e-125">CabDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="c7a4e-126">MFCMAPI 使用**DeleteEntries**方法从通讯簿容器中删除特定的条目。</span><span class="sxs-lookup"><span data-stu-id="c7a4e-126">MFCMAPI uses the **DeleteEntries** method to delete a specific entry from an address book container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7a4e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7a4e-127">See also</span></span>



[<span data-ttu-id="c7a4e-128">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="c7a4e-128">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)


[<span data-ttu-id="c7a4e-129">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c7a4e-129">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

