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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d131681ab9a49f1d25d14641855fb19c2456b0c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565408"
---
# <a name="pidtagcontactaddressbookfoldername-canonical-property"></a><span data-ttu-id="f7ed9-103">PidTagContactAddressBookFolderName 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7ed9-103">PidTagContactAddressBookFolderName Canonical Property</span></span>

  
  
<span data-ttu-id="f7ed9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7ed9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7ed9-105">包含用于通讯簿条目的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="f7ed9-105">Contains a folder name used for address book entries.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f7ed9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f7ed9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f7ed9-107">PR_CONTAB_FOLDER_NAME PR_CONTAB_FOLDER_NAME_W</span><span class="sxs-lookup"><span data-stu-id="f7ed9-107">PR_CONTAB_FOLDER_NAME, PR_CONTAB_FOLDER_NAME_W</span></span>  <br/> |
|<span data-ttu-id="f7ed9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f7ed9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f7ed9-109">0x6613</span><span class="sxs-lookup"><span data-stu-id="f7ed9-109">0x6613</span></span>  <br/> |
|<span data-ttu-id="f7ed9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f7ed9-110">Data type:</span></span>  <br/> |<span data-ttu-id="f7ed9-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="f7ed9-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="f7ed9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f7ed9-112">Area:</span></span>  <br/> |<span data-ttu-id="f7ed9-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="f7ed9-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f7ed9-114">注解</span><span class="sxs-lookup"><span data-stu-id="f7ed9-114">Remarks</span></span>

<span data-ttu-id="f7ed9-115">文件夹名称中不能使用以下字符：</span><span class="sxs-lookup"><span data-stu-id="f7ed9-115">The following characters cannot be used in folder names:</span></span>
  
<span data-ttu-id="f7ed9-116">[ ] / \ &amp; ~ ?</span><span class="sxs-lookup"><span data-stu-id="f7ed9-116">[ ] / \ &amp; ~ ?</span></span> <span data-ttu-id="f7ed9-117">\* | \<\> " ; : +</span><span class="sxs-lookup"><span data-stu-id="f7ed9-117">\* | \< \> " ; : +</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f7ed9-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f7ed9-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f7ed9-119">头文件</span><span class="sxs-lookup"><span data-stu-id="f7ed9-119">Header files</span></span>

<span data-ttu-id="f7ed9-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f7ed9-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="f7ed9-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f7ed9-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="f7ed9-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f7ed9-122">Mapitags.h</span></span>
  
> <span data-ttu-id="f7ed9-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f7ed9-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7ed9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ed9-124">See also</span></span>



[<span data-ttu-id="f7ed9-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f7ed9-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f7ed9-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7ed9-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f7ed9-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f7ed9-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f7ed9-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f7ed9-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

