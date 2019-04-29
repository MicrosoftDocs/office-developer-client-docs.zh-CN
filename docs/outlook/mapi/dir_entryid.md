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
ms.openlocfilehash: e7abcb2c86ff5cabe0b8f5664ec316244617ac09
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421233"
---
# <a name="direntryid"></a><span data-ttu-id="c238f-103">DIR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="c238f-103">DIR_ENTRYID</span></span>

  
  
<span data-ttu-id="c238f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c238f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c238f-105">介绍目录项 id 的属性。</span><span class="sxs-lookup"><span data-stu-id="c238f-105">Describes the properties of a directory entry id.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c238f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c238f-106">Header file:</span></span>  <br/> |<span data-ttu-id="c238f-107">entryid</span><span class="sxs-lookup"><span data-stu-id="c238f-107">entryid.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="c238f-108">Members</span><span class="sxs-lookup"><span data-stu-id="c238f-108">Members</span></span>

 <span data-ttu-id="c238f-109">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="c238f-109">**abFlags**</span></span>
  
> <span data-ttu-id="c238f-110">提供描述对象的信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c238f-110">A bitmask of flags that provides information describing the object.</span></span> <span data-ttu-id="c238f-111">有关详细信息, 请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。</span><span class="sxs-lookup"><span data-stu-id="c238f-111">For more information, see the description of the **abFlags** field of an [ENTRYID](entryid.md) structure.</span></span> 
    
 <span data-ttu-id="c238f-112">**muid**</span><span class="sxs-lookup"><span data-stu-id="c238f-112">**muid**</span></span>
  
> <span data-ttu-id="c238f-113">标识存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c238f-113">GUID that identifies the store provider.</span></span>
    
 <span data-ttu-id="c238f-114">**ulVersion**</span><span class="sxs-lookup"><span data-stu-id="c238f-114">**ulVersion**</span></span>
  
> <span data-ttu-id="c238f-115">**DIR_ENTRYID**结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="c238f-115">The version number of the **DIR_ENTRYID** structure.</span></span> <span data-ttu-id="c238f-116">必须设置为 CONTAB_VERSION。</span><span class="sxs-lookup"><span data-stu-id="c238f-116">Must be set to CONTAB_VERSION.</span></span> 
    
 <span data-ttu-id="c238f-117">**ulType**</span><span class="sxs-lookup"><span data-stu-id="c238f-117">**ulType**</span></span>
  
> <span data-ttu-id="c238f-118">表示目录项 ID 类型的整数。</span><span class="sxs-lookup"><span data-stu-id="c238f-118">An integer representing the directory entry ID type.</span></span> <span data-ttu-id="c238f-119">它必须是下列值之一:</span><span class="sxs-lookup"><span data-stu-id="c238f-119">It must be one of the following values:</span></span>
    
|<span data-ttu-id="c238f-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="c238f-120">**Name**</span></span>|<span data-ttu-id="c238f-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="c238f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c238f-122">CONTAB_ROOT</span><span class="sxs-lookup"><span data-stu-id="c238f-122">CONTAB_ROOT</span></span>  <br/> |<span data-ttu-id="c238f-123">MAPI 通讯簿的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="c238f-123">The root folder for a MAPI address book.</span></span>  <br/> |
|<span data-ttu-id="c238f-124">CONTAB_SUBROOT</span><span class="sxs-lookup"><span data-stu-id="c238f-124">CONTAB_SUBROOT</span></span>  <br/> |<span data-ttu-id="c238f-125">MAPI 通讯簿对象的根文件夹内包含一个子文件。</span><span class="sxs-lookup"><span data-stu-id="c238f-125">A subfolder contained within the root folder of the MAPI address book object.</span></span>  <br/> |
|<span data-ttu-id="c238f-126">CONTAB_CONTAINER</span><span class="sxs-lookup"><span data-stu-id="c238f-126">CONTAB_CONTAINER</span></span>  <br/> |<span data-ttu-id="c238f-127">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="c238f-127">An address book container object.</span></span>  <br/> |
   
 <span data-ttu-id="c238f-128">**muidID**</span><span class="sxs-lookup"><span data-stu-id="c238f-128">**muidID**</span></span>
  
> <span data-ttu-id="c238f-129">标识登录对象的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c238f-129">A GUID that identifies the logon object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c238f-130">说明</span><span class="sxs-lookup"><span data-stu-id="c238f-130">Remarks</span></span>

<span data-ttu-id="c238f-131">除**ulType**成员之外, 结构**DIR_ENTRYID**和[CONTAB_ENTRYID](contab_entryid.md)相同。</span><span class="sxs-lookup"><span data-stu-id="c238f-131">The structures **DIR_ENTRYID** and [CONTAB_ENTRYID](contab_entryid.md) are identical, except for the **ulType** member.</span></span> <span data-ttu-id="c238f-132">**ulType**成员的内容确定哪种结构适用于其余字段。</span><span class="sxs-lookup"><span data-stu-id="c238f-132">The contents of the **ulType** member determine which structure is appropriate for the remaining fields.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c238f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c238f-133">See also</span></span>



[<span data-ttu-id="c238f-134">CONTAB_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="c238f-134">CONTAB_ENTRYID</span></span>](contab_entryid.md)


[<span data-ttu-id="c238f-135">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c238f-135">MAPI Structures</span></span>](mapi-structures.md)

