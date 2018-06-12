---
title: PidTagContactAddressBookFolderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookFolderName
api_type:
- HeaderDef
ms.assetid: 6149da2f-6e42-429c-bcdb-d517d21df720
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a4a72e6d5136d7e78648cb62849f7162b7b35f6c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777426"
---
# <a name="pidtagcontactaddressbookfoldername-canonical-property"></a><span data-ttu-id="724d9-103">PidTagContactAddressBookFolderName 规范属性</span><span class="sxs-lookup"><span data-stu-id="724d9-103">PidTagContactAddressBookFolderName Canonical Property</span></span>

  
  
<span data-ttu-id="724d9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="724d9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="724d9-105">包含用于通讯簿条目的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="724d9-105">Contains a folder name used for address book entries.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="724d9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="724d9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="724d9-107">PR_CONTAB_FOLDER_NAME PR_CONTAB_FOLDER_NAME_W</span><span class="sxs-lookup"><span data-stu-id="724d9-107">PR_CONTAB_FOLDER_NAME, PR_CONTAB_FOLDER_NAME_W</span></span>  <br/> |
|<span data-ttu-id="724d9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="724d9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="724d9-109">0x6613</span><span class="sxs-lookup"><span data-stu-id="724d9-109">0x6613</span></span>  <br/> |
|<span data-ttu-id="724d9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="724d9-110">Data type:</span></span>  <br/> |<span data-ttu-id="724d9-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="724d9-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="724d9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="724d9-112">Area:</span></span>  <br/> |<span data-ttu-id="724d9-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="724d9-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="724d9-114">备注</span><span class="sxs-lookup"><span data-stu-id="724d9-114">Remarks</span></span>

<span data-ttu-id="724d9-115">文件夹名称中不能使用以下字符：</span><span class="sxs-lookup"><span data-stu-id="724d9-115">The following characters cannot be used in folder names:</span></span>
  
<span data-ttu-id="724d9-116">[ ] / \ &amp; ~ ?</span><span class="sxs-lookup"><span data-stu-id="724d9-116">[ ] / \ &amp; ~ ?</span></span> <span data-ttu-id="724d9-117">\* | \<\> " ; : +</span><span class="sxs-lookup"><span data-stu-id="724d9-117">\* | \< \> " ; : +</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="724d9-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="724d9-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="724d9-119">头文件</span><span class="sxs-lookup"><span data-stu-id="724d9-119">Header files</span></span>

<span data-ttu-id="724d9-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="724d9-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="724d9-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="724d9-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="724d9-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="724d9-122">Mapitags.h</span></span>
  
> <span data-ttu-id="724d9-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="724d9-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="724d9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="724d9-124">See also</span></span>



[<span data-ttu-id="724d9-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="724d9-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="724d9-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="724d9-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="724d9-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="724d9-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="724d9-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="724d9-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

