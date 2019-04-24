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
ms.openlocfilehash: 2db7dba67e7b71df6921ecd97189255a0ef7823a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309546"
---
# <a name="iprofadmingetprofiletable"></a><span data-ttu-id="3f8eb-103">IProfAdmin::GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="3f8eb-103">IProfAdmin::GetProfileTable</span></span>

  
  
<span data-ttu-id="3f8eb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f8eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f8eb-105">提供对配置文件表 (包含所有可用配置文件的相关信息的表) 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-105">Provides access to the profile table, a table that contains information about all of the available profiles.</span></span>
  
```cpp
HRESULT GetProfileTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="3f8eb-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f8eb-106">Parameters</span></span>

 <span data-ttu-id="3f8eb-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3f8eb-107">_ulFlags_</span></span>
  
> <span data-ttu-id="3f8eb-108">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="3f8eb-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="3f8eb-109">_lppTable_</span></span>
  
> <span data-ttu-id="3f8eb-110">排除指向指向配置文件表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-110">[out] A pointer to a pointer to the profile table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3f8eb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3f8eb-111">Return value</span></span>

<span data-ttu-id="3f8eb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f8eb-112">S_OK</span></span> 
  
> <span data-ttu-id="3f8eb-113">已成功检索配置文件表。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-113">The profile table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3f8eb-114">注解</span><span class="sxs-lookup"><span data-stu-id="3f8eb-114">Remarks</span></span>

<span data-ttu-id="3f8eb-115">**IProfAdmin:: GetProfileTable**方法提供对配置文件表的访问, 其中每个可用的配置文件在其中占一行。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-115">The **IProfAdmin::GetProfileTable** method provides access to the profile table, which contains one row for every available profile.</span></span> <span data-ttu-id="3f8eb-116">每行中仅有两列: 配置文件的显示名称和指示是否为默认配置文件的标志。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-116">There are only two columns in each row: the profile's display name, and a flag that indicates whether the profile is the default.</span></span> 
  
<span data-ttu-id="3f8eb-117">配置文件表中不包含已删除或正在使用但已标记为删除的配置文件。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-117">Profiles that have been deleted, or that are in use but have been marked for deletion, are not included in the profile table.</span></span> <span data-ttu-id="3f8eb-118">配置文件表是静态的;后续的配置文件添加和删除不会反映在表中。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-118">The profile table is static; subsequent additions and deletions of profiles are not reflected in the table.</span></span> 
  
<span data-ttu-id="3f8eb-119">如果不存在任何配置文件, **GetProfileTable**将返回一个包含零行的表。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-119">If no profiles exist, **GetProfileTable** returns a table with zero rows.</span></span> 
  
<span data-ttu-id="3f8eb-120">有关配置文件表的详细信息, 请参阅[profile Tables 表](profile-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-120">For more information about the profile table, see [Profile Tables](profile-tables.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3f8eb-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3f8eb-121">MFCMAPI reference</span></span>

<span data-ttu-id="3f8eb-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3f8eb-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="3f8eb-123">**File**</span></span>|<span data-ttu-id="3f8eb-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="3f8eb-124">**Function**</span></span>|<span data-ttu-id="3f8eb-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="3f8eb-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f8eb-126">MainDlg</span><span class="sxs-lookup"><span data-stu-id="3f8eb-126">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="3f8eb-127">CMainDlg:: OnShowProfiles</span><span class="sxs-lookup"><span data-stu-id="3f8eb-127">CMainDlg::OnShowProfiles</span></span>  <br/> |<span data-ttu-id="3f8eb-128">MFCMAPI 使用**IProfAdmin:: GetProfileTable**方法获取要在新对话框中显示的配置文件表。</span><span class="sxs-lookup"><span data-stu-id="3f8eb-128">MFCMAPI uses the **IProfAdmin::GetProfileTable** method to get the profile table to display in a new dialog box.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3f8eb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f8eb-129">See also</span></span>



[<span data-ttu-id="3f8eb-130">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3f8eb-130">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="3f8eb-131">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="3f8eb-131">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="3f8eb-132">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3f8eb-132">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="3f8eb-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3f8eb-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

