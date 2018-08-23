---
title: DIR_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9e055269-f3bf-4b64-8384-3cbc372c0b34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ef3f37ab266469e83434d5d9bd0bc7e2ef897fa
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583342"
---
# <a name="direntryid"></a><span data-ttu-id="b9851-103">DIR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b9851-103">DIR_ENTRYID</span></span>

  
  
<span data-ttu-id="b9851-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9851-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9851-105">介绍目录条目 id 的属性。</span><span class="sxs-lookup"><span data-stu-id="b9851-105">Describes the properties of a directory entry id.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b9851-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b9851-106">Header file:</span></span>  <br/> |<span data-ttu-id="b9851-107">entryid.h</span><span class="sxs-lookup"><span data-stu-id="b9851-107">entryid.h</span></span>  <br/> |
   
```cpp
#pragma pack(4)
typedef struct _dir_entryid
{
    BYTE abFlags[4]; 
    MAPIUID muid; 
    ULONG ulVersion; 
    ULONG ulType; 
    MAPIUID muidID; 
}   DIR_ENTRYID, *LPDIR_ENTRYID; 
#pragma pack()
```

## <a name="members"></a><span data-ttu-id="b9851-108">Members</span><span class="sxs-lookup"><span data-stu-id="b9851-108">Members</span></span>

 <span data-ttu-id="b9851-109">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="b9851-109">**abFlags**</span></span>
  
> <span data-ttu-id="b9851-110">位掩码的标志，提供描述对象的信息。</span><span class="sxs-lookup"><span data-stu-id="b9851-110">A bitmask of flags that provides information describing the object.</span></span> <span data-ttu-id="b9851-111">有关详细信息，请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。</span><span class="sxs-lookup"><span data-stu-id="b9851-111">For more information, see the description of the **abFlags** field of an [ENTRYID](entryid.md) structure.</span></span> 
    
 <span data-ttu-id="b9851-112">**muid**</span><span class="sxs-lookup"><span data-stu-id="b9851-112">**muid**</span></span>
  
> <span data-ttu-id="b9851-113">标识的存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b9851-113">GUID that identifies the store provider.</span></span>
    
 <span data-ttu-id="b9851-114">**ulVersion**</span><span class="sxs-lookup"><span data-stu-id="b9851-114">**ulVersion**</span></span>
  
> <span data-ttu-id="b9851-115">**DIR_ENTRYID**结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="b9851-115">The version number of the **DIR_ENTRYID** structure.</span></span> <span data-ttu-id="b9851-116">必须设置为 CONTAB_VERSION。</span><span class="sxs-lookup"><span data-stu-id="b9851-116">Must be set to CONTAB_VERSION.</span></span> 
    
 <span data-ttu-id="b9851-117">**ulType**</span><span class="sxs-lookup"><span data-stu-id="b9851-117">**ulType**</span></span>
  
> <span data-ttu-id="b9851-118">表示目录条目 ID 类型的整数。</span><span class="sxs-lookup"><span data-stu-id="b9851-118">An integer representing the directory entry ID type.</span></span> <span data-ttu-id="b9851-119">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b9851-119">It must be one of the following values:</span></span>
    
|<span data-ttu-id="b9851-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="b9851-120">**Name**</span></span>|<span data-ttu-id="b9851-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9851-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9851-122">CONTAB_ROOT</span><span class="sxs-lookup"><span data-stu-id="b9851-122">CONTAB_ROOT</span></span>  <br/> |<span data-ttu-id="b9851-123">MAPI 通讯簿根文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9851-123">The root folder for a MAPI address book.</span></span>  <br/> |
|<span data-ttu-id="b9851-124">CONTAB_SUBROOT</span><span class="sxs-lookup"><span data-stu-id="b9851-124">CONTAB_SUBROOT</span></span>  <br/> |<span data-ttu-id="b9851-125">MAPI 通讯簿对象的根文件夹中包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9851-125">A subfolder contained within the root folder of the MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="b9851-126">CONTAB_CONTAINER</span><span class="sxs-lookup"><span data-stu-id="b9851-126">CONTAB_CONTAINER</span></span>  <br/> |<span data-ttu-id="b9851-127">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="b9851-127">An address book container object.</span></span>  <br/> |
   
 <span data-ttu-id="b9851-128">**muidID**</span><span class="sxs-lookup"><span data-stu-id="b9851-128">**muidID**</span></span>
  
> <span data-ttu-id="b9851-129">标识登录对象的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b9851-129">A GUID that identifies the logon object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b9851-130">注解</span><span class="sxs-lookup"><span data-stu-id="b9851-130">Remarks</span></span>

<span data-ttu-id="b9851-131">结构**DIR_ENTRYID**和[CONTAB_ENTRYID](contab_entryid.md)完全相同，除了**ulType**成员。</span><span class="sxs-lookup"><span data-stu-id="b9851-131">The structures **DIR_ENTRYID** and [CONTAB_ENTRYID](contab_entryid.md) are identical, except for the **ulType** member.</span></span> <span data-ttu-id="b9851-132">**UlType**成员的内容确定适合剩余字段的结构。</span><span class="sxs-lookup"><span data-stu-id="b9851-132">The contents of the **ulType** member determine which structure is appropriate for the remaining fields.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9851-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9851-133">See also</span></span>



[<span data-ttu-id="b9851-134">CONTAB_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b9851-134">CONTAB_ENTRYID</span></span>](contab_entryid.md)


[<span data-ttu-id="b9851-135">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b9851-135">MAPI Structures</span></span>](mapi-structures.md)

