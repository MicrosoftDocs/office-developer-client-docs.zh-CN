---
title: IProfAdminGetProfileTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetProfileTable
api_type:
- COM
ms.assetid: cebccd2d-8215-486e-9964-7fc42412cec6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b1b037cf24c1bb5a0c84da3d59892ab15763f37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588242"
---
# <a name="iprofadmingetprofiletable"></a><span data-ttu-id="be034-103">IProfAdmin::GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="be034-103">IProfAdmin::GetProfileTable</span></span>

  
  
<span data-ttu-id="be034-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be034-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be034-105">提供对配置文件表中，一个表，包含有关所有可用的配置文件信息的访问。</span><span class="sxs-lookup"><span data-stu-id="be034-105">Provides access to the profile table, a table that contains information about all of the available profiles.</span></span>
  
```cpp
HRESULT GetProfileTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="be034-106">参数</span><span class="sxs-lookup"><span data-stu-id="be034-106">Parameters</span></span>

 <span data-ttu-id="be034-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="be034-107">_ulFlags_</span></span>
  
> <span data-ttu-id="be034-108">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="be034-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="be034-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="be034-109">_lppTable_</span></span>
  
> <span data-ttu-id="be034-110">[输出]指向配置文件表格的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="be034-110">[out] A pointer to a pointer to the profile table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="be034-111">返回值</span><span class="sxs-lookup"><span data-stu-id="be034-111">Return value</span></span>

<span data-ttu-id="be034-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="be034-112">S_OK</span></span> 
  
> <span data-ttu-id="be034-113">已成功检索配置文件表。</span><span class="sxs-lookup"><span data-stu-id="be034-113">The profile table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="be034-114">注解</span><span class="sxs-lookup"><span data-stu-id="be034-114">Remarks</span></span>

<span data-ttu-id="be034-115">**IProfAdmin::GetProfileTable**方法提供了对配置文件表，其中包含一行，每个可用的配置文件的访问。</span><span class="sxs-lookup"><span data-stu-id="be034-115">The **IProfAdmin::GetProfileTable** method provides access to the profile table, which contains one row for every available profile.</span></span> <span data-ttu-id="be034-116">在每行中有只有两个列： 配置文件的显示名称和一个指示的配置文件是否是默认的标志。</span><span class="sxs-lookup"><span data-stu-id="be034-116">There are only two columns in each row: the profile's display name, and a flag that indicates whether the profile is the default.</span></span> 
  
<span data-ttu-id="be034-117">配置文件已被删除，或的仍在使用，但已标记为删除，不包括在配置文件表。</span><span class="sxs-lookup"><span data-stu-id="be034-117">Profiles that have been deleted, or that are in use but have been marked for deletion, are not included in the profile table.</span></span> <span data-ttu-id="be034-118">配置文件表是静态;后续的添加和配置文件的删除操作不会反映表中。</span><span class="sxs-lookup"><span data-stu-id="be034-118">The profile table is static; subsequent additions and deletions of profiles are not reflected in the table.</span></span> 
  
<span data-ttu-id="be034-119">如果没有配置文件存在，则**GetProfileTable**将返回具有零个行的表。</span><span class="sxs-lookup"><span data-stu-id="be034-119">If no profiles exist, **GetProfileTable** returns a table with zero rows.</span></span> 
  
<span data-ttu-id="be034-120">有关配置文件表的详细信息，请参阅[配置文件表](profile-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="be034-120">For more information about the profile table, see [Profile Tables](profile-tables.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="be034-121">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="be034-121">MFCMAPI reference</span></span>

<span data-ttu-id="be034-122">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="be034-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="be034-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="be034-123">**File**</span></span>|<span data-ttu-id="be034-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="be034-124">**Function**</span></span>|<span data-ttu-id="be034-125">**Comment**</span><span class="sxs-lookup"><span data-stu-id="be034-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="be034-126">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="be034-126">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="be034-127">CMainDlg::OnShowProfiles</span><span class="sxs-lookup"><span data-stu-id="be034-127">CMainDlg::OnShowProfiles</span></span>  <br/> |<span data-ttu-id="be034-128">MFCMAPI 使用**IProfAdmin::GetProfileTable**方法来获取要在新的对话框中显示的配置文件表。</span><span class="sxs-lookup"><span data-stu-id="be034-128">MFCMAPI uses the **IProfAdmin::GetProfileTable** method to get the profile table to display in a new dialog box.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="be034-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be034-129">See also</span></span>



[<span data-ttu-id="be034-130">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="be034-130">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="be034-131">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="be034-131">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="be034-132">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="be034-132">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="be034-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="be034-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

