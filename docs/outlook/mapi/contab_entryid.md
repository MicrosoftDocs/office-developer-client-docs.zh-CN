---
title: CONTAB_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84251222-dac4-4f4d-97b9-aa0e2cd26c44
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2a204f76b62c8c6bc6d8a4e793c936a0184dc65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424082"
---
# <a name="contab_entryid"></a><span data-ttu-id="54b14-103">CONTAB_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="54b14-103">CONTAB_ENTRYID</span></span>

  
  
<span data-ttu-id="54b14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54b14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54b14-105">包含联系人文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="54b14-105">Contains the entry ID of the contacts folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="54b14-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="54b14-106">Header file:</span></span>  <br/> |<span data-ttu-id="54b14-107">msomapiutil.h</span><span class="sxs-lookup"><span data-stu-id="54b14-107">msomapiutil.h</span></span>  <br/> |
   
```cpp
#pragma pack(4) 
typedef struct _contab_entryid
{
    BYTE abFlags[4];
    MAPIUID muid;
    ULONG ulVersion;
    ULONG ulType;
    ULONG ulIndex;
    ULONG cbeid;
    BYTE abeid[1];
}   CONTAB_ENTRYID, *LPCONTAB_ENTRYID;
#pragma pack() 
```

## <a name="members"></a><span data-ttu-id="54b14-108">Members</span><span class="sxs-lookup"><span data-stu-id="54b14-108">Members</span></span>

 <span data-ttu-id="54b14-109">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="54b14-109">**abFlags**</span></span>
  
> <span data-ttu-id="54b14-110">提供描述对象的信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="54b14-110">A bitmask of flags that provides information describing the object.</span></span> <span data-ttu-id="54b14-111">有关详细信息，请参阅 [ENTRYID](entryid.md)结构的 **abFlags** 字段的说明。</span><span class="sxs-lookup"><span data-stu-id="54b14-111">For more information, see the description of the **abFlags** field of an [ENTRYID](entryid.md) structure.</span></span> 
    
 <span data-ttu-id="54b14-112">**muid**</span><span class="sxs-lookup"><span data-stu-id="54b14-112">**muid**</span></span>
  
> <span data-ttu-id="54b14-113">标识存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="54b14-113">GUID that identifies the store provider.</span></span>
    
 <span data-ttu-id="54b14-114">**ulVersion**</span><span class="sxs-lookup"><span data-stu-id="54b14-114">**ulVersion**</span></span>
  
> <span data-ttu-id="54b14-115">该 **结构CONTAB_ENTRYID版本号** 。</span><span class="sxs-lookup"><span data-stu-id="54b14-115">The version number of the **CONTAB_ENTRYID** structure.</span></span> <span data-ttu-id="54b14-116">必须设置为 CONTAB_VERSION。</span><span class="sxs-lookup"><span data-stu-id="54b14-116">Must be set to CONTAB_VERSION.</span></span> 
    
 <span data-ttu-id="54b14-117">**ulType**</span><span class="sxs-lookup"><span data-stu-id="54b14-117">**ulType**</span></span>
  
> <span data-ttu-id="54b14-118">一个代表联系人条目 ID 类型的整数。</span><span class="sxs-lookup"><span data-stu-id="54b14-118">An integer representing the contact entry ID type.</span></span> <span data-ttu-id="54b14-119">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="54b14-119">It must be one of the following values:</span></span>
    
|<span data-ttu-id="54b14-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="54b14-120">**Name**</span></span>|<span data-ttu-id="54b14-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="54b14-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="54b14-122">CONTAB_USER</span><span class="sxs-lookup"><span data-stu-id="54b14-122">CONTAB_USER</span></span>  <br/> |<span data-ttu-id="54b14-123">消息传递用户对象。</span><span class="sxs-lookup"><span data-stu-id="54b14-123">A messaging user object.</span></span>  <br/> |
|<span data-ttu-id="54b14-124">CONTAB_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="54b14-124">CONTAB_DISTLIST</span></span>  <br/> |<span data-ttu-id="54b14-125">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="54b14-125">A distribution list object.</span></span>  <br/> |
   
 <span data-ttu-id="54b14-126">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="54b14-126">**ulIndex**</span></span>
  
> <span data-ttu-id="54b14-127">电子邮件属性子集的索引。</span><span class="sxs-lookup"><span data-stu-id="54b14-127">The index into the email property subset.</span></span>
    
 <span data-ttu-id="54b14-128">**c一d**</span><span class="sxs-lookup"><span data-stu-id="54b14-128">**cbeid**</span></span>
  
> <span data-ttu-id="54b14-129">与联系人通讯簿中与此条目关联的联系人邮件的条目标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="54b14-129">The size of the entry identifier of the Contact message associated with this entry in the Contacts Address Book.</span></span>
    
 <span data-ttu-id="54b14-130">**a一5d**</span><span class="sxs-lookup"><span data-stu-id="54b14-130">**abeid**</span></span>
  
> <span data-ttu-id="54b14-131">与联系人通讯簿中的此项相关联的联系人邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="54b14-131">The entry identifier of the Contact message associated with this entry in the Contacts Address Book.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="54b14-132">备注</span><span class="sxs-lookup"><span data-stu-id="54b14-132">Remarks</span></span>

<span data-ttu-id="54b14-133">联系人通讯簿是一个通讯簿，其中包含具有电子邮件地址或传真号码的"联系人"文件夹中的所有联系人项目。</span><span class="sxs-lookup"><span data-stu-id="54b14-133">A Contacts Address Book is an Address Book that contains all the contact items in a Contacts folder that have either an email address or a fax number.</span></span> <span data-ttu-id="54b14-134">联系人通讯簿中的每个条目都与电子邮件地址或传真号码关联。</span><span class="sxs-lookup"><span data-stu-id="54b14-134">Each entry in a Contacts Address Book is associated with either an email address or a fax number.</span></span> <span data-ttu-id="54b14-135">由于联系人项目可以有最多三个电子邮件地址和三个传真号码，因此联系人项目可以在相应的联系人通讯簿中用最多六个条目表示。</span><span class="sxs-lookup"><span data-stu-id="54b14-135">Since a contact item can have up to three email addresses and three fax numbers, a contact item can be represented by up to six entries in the corresponding Contacts Address Book.</span></span>
  
<span data-ttu-id="54b14-136">联系人通讯簿的用途是支持用户向"联系人"文件夹中的联系人发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="54b14-136">The purpose of a Contacts Address Book is to support users addressing email messages to contacts in a Contacts folder.</span></span> <span data-ttu-id="54b14-137">支持联系人通讯簿Microsoft Outlook 2010 Microsoft Outlook 2013支持contab32.dll。</span><span class="sxs-lookup"><span data-stu-id="54b14-137">The Contacts Address Book provider that Microsoft Outlook 2010 and Microsoft Outlook 2013 support is contab32.dll.</span></span>
  
<span data-ttu-id="54b14-138">the **CONTAB_ENTRYID** structure supports a subset of the information that is present in the underlying MAPI Contact message.</span><span class="sxs-lookup"><span data-stu-id="54b14-138">The **CONTAB_ENTRYID** structure supports a subset of the information that is present in the underlying MAPI Contact message.</span></span> <span data-ttu-id="54b14-139">它标识与特定联系人通讯簿条目关联的联系人邮件。</span><span class="sxs-lookup"><span data-stu-id="54b14-139">It identifies the Contact message that a particular Contacts Address Book entry is associated with.</span></span> 
  
<span data-ttu-id="54b14-140">仅 **当** **ulType** 字段值设置为 CONTAB_DISTLIST 或 CONTAB_USER 时，c一d 和 **add** 字段才CONTAB_USER。</span><span class="sxs-lookup"><span data-stu-id="54b14-140">The **cbeid** and **abeid** fields are only valid when the **ulType** field value is set to CONTAB_DISTLIST or CONTAB_USER.</span></span> <span data-ttu-id="54b14-141">当 **ulType** 字段值设置为 CONTAB_ROOT、CONTAB_SUBROOT 或 CONTAB_CONTAINER 时，DIR_ENTRYID相反。 [](dir_entryid.md)</span><span class="sxs-lookup"><span data-stu-id="54b14-141">When the **ulType** field value is set to CONTAB_ROOT, CONTAB_SUBROOT, or CONTAB_CONTAINER, the [DIR_ENTRYID](dir_entryid.md) structure should be used instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="54b14-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54b14-142">See also</span></span>



[<span data-ttu-id="54b14-143">DIR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="54b14-143">DIR_ENTRYID</span></span>](dir_entryid.md)


[<span data-ttu-id="54b14-144">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="54b14-144">MAPI Structures</span></span>](mapi-structures.md)

