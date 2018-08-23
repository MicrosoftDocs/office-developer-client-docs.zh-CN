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
ms.openlocfilehash: ff088dc5bf62f407692c9eec649ff388f79d549d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567151"
---
# <a name="contabentryid"></a><span data-ttu-id="750fa-103">CONTAB_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="750fa-103">CONTAB_ENTRYID</span></span>

  
  
<span data-ttu-id="750fa-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="750fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="750fa-105">包含联系人文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="750fa-105">Contains the entry ID of the contacts folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="750fa-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="750fa-106">Header file:</span></span>  <br/> |<span data-ttu-id="750fa-107">msomapiutil.h</span><span class="sxs-lookup"><span data-stu-id="750fa-107">msomapiutil.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="750fa-108">Members</span><span class="sxs-lookup"><span data-stu-id="750fa-108">Members</span></span>

 <span data-ttu-id="750fa-109">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="750fa-109">**abFlags**</span></span>
  
> <span data-ttu-id="750fa-110">位掩码的标志，提供描述对象的信息。</span><span class="sxs-lookup"><span data-stu-id="750fa-110">A bitmask of flags that provides information describing the object.</span></span> <span data-ttu-id="750fa-111">有关详细信息，请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。</span><span class="sxs-lookup"><span data-stu-id="750fa-111">For more information, see the description of the **abFlags** field of an [ENTRYID](entryid.md) structure.</span></span> 
    
 <span data-ttu-id="750fa-112">**muid**</span><span class="sxs-lookup"><span data-stu-id="750fa-112">**muid**</span></span>
  
> <span data-ttu-id="750fa-113">标识的存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="750fa-113">GUID that identifies the store provider.</span></span>
    
 <span data-ttu-id="750fa-114">**ulVersion**</span><span class="sxs-lookup"><span data-stu-id="750fa-114">**ulVersion**</span></span>
  
> <span data-ttu-id="750fa-115">**CONTAB_ENTRYID**结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="750fa-115">The version number of the **CONTAB_ENTRYID** structure.</span></span> <span data-ttu-id="750fa-116">必须设置为 CONTAB_VERSION。</span><span class="sxs-lookup"><span data-stu-id="750fa-116">Must be set to CONTAB_VERSION.</span></span> 
    
 <span data-ttu-id="750fa-117">**ulType**</span><span class="sxs-lookup"><span data-stu-id="750fa-117">**ulType**</span></span>
  
> <span data-ttu-id="750fa-118">一个代表联系人项 ID 类型的整数。</span><span class="sxs-lookup"><span data-stu-id="750fa-118">An integer representing the contact entry ID type.</span></span> <span data-ttu-id="750fa-119">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="750fa-119">It must be one of the following values:</span></span>
    
|<span data-ttu-id="750fa-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="750fa-120">**Name**</span></span>|<span data-ttu-id="750fa-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="750fa-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="750fa-122">CONTAB_USER</span><span class="sxs-lookup"><span data-stu-id="750fa-122">CONTAB_USER</span></span>  <br/> |<span data-ttu-id="750fa-123">消息的用户对象。</span><span class="sxs-lookup"><span data-stu-id="750fa-123">A messaging user object.</span></span>  <br/> |
|<span data-ttu-id="750fa-124">CONTAB_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="750fa-124">CONTAB_DISTLIST</span></span>  <br/> |<span data-ttu-id="750fa-125">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="750fa-125">A distribution list object.</span></span>  <br/> |
   
 <span data-ttu-id="750fa-126">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="750fa-126">**ulIndex**</span></span>
  
> <span data-ttu-id="750fa-127">到电子邮件属性子集的索引。</span><span class="sxs-lookup"><span data-stu-id="750fa-127">The index into the email property subset.</span></span>
    
 <span data-ttu-id="750fa-128">**cbeid**</span><span class="sxs-lookup"><span data-stu-id="750fa-128">**cbeid**</span></span>
  
> <span data-ttu-id="750fa-129">联系人消息与联系人通讯簿中的此条目关联的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="750fa-129">The size of the entry identifier of the Contact message associated with this entry in the Contacts Address Book.</span></span>
    
 <span data-ttu-id="750fa-130">**abeid**</span><span class="sxs-lookup"><span data-stu-id="750fa-130">**abeid**</span></span>
  
> <span data-ttu-id="750fa-131">联系人消息与联系人通讯簿中的此条目关联的项标识符。</span><span class="sxs-lookup"><span data-stu-id="750fa-131">The entry identifier of the Contact message associated with this entry in the Contacts Address Book.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="750fa-132">注解</span><span class="sxs-lookup"><span data-stu-id="750fa-132">Remarks</span></span>

<span data-ttu-id="750fa-133">联系人通讯簿通讯簿包含联系人文件夹中的电子邮件地址或传真号码的所有联系人项目。</span><span class="sxs-lookup"><span data-stu-id="750fa-133">A Contacts Address Book is an Address Book that contains all the contact items in a Contacts folder that have either an email address or a fax number.</span></span> <span data-ttu-id="750fa-134">每个联系人通讯簿中的项相关联的电子邮件地址或传真号码。</span><span class="sxs-lookup"><span data-stu-id="750fa-134">Each entry in a Contacts Address Book is associated with either an email address or a fax number.</span></span> <span data-ttu-id="750fa-135">由于联系人项可以具有三个电子邮件地址和三个传真号码，可以通过在相应的联系人通讯簿中的最多为六个条目表示联系人项目。</span><span class="sxs-lookup"><span data-stu-id="750fa-135">Since a contact item can have up to three email addresses and three fax numbers, a contact item can be represented by up to six entries in the corresponding Contacts Address Book.</span></span>
  
<span data-ttu-id="750fa-136">联系人通讯簿旨在支持寻址到联系人文件夹中的联系人的电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="750fa-136">The purpose of a Contacts Address Book is to support users addressing email messages to contacts in a Contacts folder.</span></span> <span data-ttu-id="750fa-137">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持的联系人通讯簿提供程序是 contab32.dll。</span><span class="sxs-lookup"><span data-stu-id="750fa-137">The Contacts Address Book provider that Microsoft Outlook 2010 and Microsoft Outlook 2013 support is contab32.dll.</span></span>
  
<span data-ttu-id="750fa-138">**CONTAB_ENTRYID**结构支持基础的 MAPI 联系人消息中出现的信息的子集。</span><span class="sxs-lookup"><span data-stu-id="750fa-138">The **CONTAB_ENTRYID** structure supports a subset of the information that is present in the underlying MAPI Contact message.</span></span> <span data-ttu-id="750fa-139">它标识联系人邮件与关联的特定的联系人通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="750fa-139">It identifies the Contact message that a particular Contacts Address Book entry is associated with.</span></span> 
  
<span data-ttu-id="750fa-140">当**ulType**字段值设置为 CONTAB_DISTLIST 或 CONTAB_USER **cbeid**和**abeid**字段才有效。</span><span class="sxs-lookup"><span data-stu-id="750fa-140">The **cbeid** and **abeid** fields are only valid when the **ulType** field value is set to CONTAB_DISTLIST or CONTAB_USER.</span></span> <span data-ttu-id="750fa-141">如果**ulType**字段值设置为 CONTAB_ROOT、 CONTAB_SUBROOT 或 CONTAB_CONTAINER， [DIR_ENTRYID](dir_entryid.md)结构应改用。</span><span class="sxs-lookup"><span data-stu-id="750fa-141">When the **ulType** field value is set to CONTAB_ROOT, CONTAB_SUBROOT, or CONTAB_CONTAINER, the [DIR_ENTRYID](dir_entryid.md) structure should be used instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="750fa-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="750fa-142">See also</span></span>



[<span data-ttu-id="750fa-143">DIR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="750fa-143">DIR_ENTRYID</span></span>](dir_entryid.md)


[<span data-ttu-id="750fa-144">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="750fa-144">MAPI Structures</span></span>](mapi-structures.md)

