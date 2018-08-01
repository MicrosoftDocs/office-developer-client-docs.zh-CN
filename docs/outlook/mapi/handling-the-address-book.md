---
title: 处理通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b685244a-fe1b-4416-85d3-4bd86ccbc3aa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6ef441b4315ef21f8b16dc062596bc7f1e526e1d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775066"
---
# <a name="handling-the-address-book"></a><span data-ttu-id="a10a2-103">处理通讯簿</span><span class="sxs-lookup"><span data-stu-id="a10a2-103">Handling the address book</span></span>
  
<span data-ttu-id="a10a2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a10a2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a10a2-105">处理 MAPI 通讯簿提取条目要用作邮件收件人，修改收件人属性创建 one-offs，并显示一个或多个通用的地址对话框添加邮件用户或通讯组列表，以便可以包括用户可以浏览地址信息并进行更改。</span><span class="sxs-lookup"><span data-stu-id="a10a2-105">Handling the MAPI address book can include extracting entries to be used as message recipients, modifying recipient properties, adding messaging users or distribution lists, creating one-offs, and displaying one or more of the common address dialog boxes to allow users to browse address information and make changes.</span></span>

- <span data-ttu-id="a10a2-106">[打开在通讯簿](opening-the-address-book.md)： 介绍如何使用 MAPI 打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="a10a2-106">[Opening the Address Book](opening-the-address-book.md): Describes how to use MAPI to open an address book.</span></span>
    
- <span data-ttu-id="a10a2-107">[显示通用的地址对话框](displaying-the-common-address-dialog-box.md)： 介绍如何显示不同的地址簿容器。</span><span class="sxs-lookup"><span data-stu-id="a10a2-107">[Displaying the Common Address Dialog Box](displaying-the-common-address-dialog-box.md): Describes how to display different address book containers.</span></span>
    
- <span data-ttu-id="a10a2-108">[打开通讯簿容器](opening-an-address-book-container.md)： 介绍如何打开不同的地址簿容器。</span><span class="sxs-lookup"><span data-stu-id="a10a2-108">[Opening an Address Book Container](opening-an-address-book-container.md): Describes how to open different address book containers.</span></span>
    
- <span data-ttu-id="a10a2-109">[设置通讯簿选项](setting-address-book-options.md)： 介绍如何设置描述使用通讯簿选项的属性。</span><span class="sxs-lookup"><span data-stu-id="a10a2-109">[Setting Address Book Options](setting-address-book-options.md): Describes how to set the properties that describe options for using the address book.</span></span>
    
- <span data-ttu-id="a10a2-110">[创建收件人](creating-a-recipient.md)： 介绍如何在撰写邮件时创建收件人并将项添加到可修改通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="a10a2-110">[Creating a Recipient](creating-a-recipient.md): Describes how to create recipients when addressing messages and adding entries to modifiable address book containers.</span></span>
    
- <span data-ttu-id="a10a2-111">[创建通讯组列表](creating-a-distribution-list.md)： 介绍如何到可修改容器中创建通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a10a2-111">[Creating a Distribution List](creating-a-distribution-list.md): Describes how to create a distribution list into a modifiable container.</span></span>
    
- <span data-ttu-id="a10a2-112">[复制收件人](copying-a-recipient.md)： 介绍如何将收件人复制到另一个容器或相同的容器。</span><span class="sxs-lookup"><span data-stu-id="a10a2-112">[Copying a Recipient](copying-a-recipient.md): Describes how to copy recipients from one container into another or the same container.</span></span>
    
- <span data-ttu-id="a10a2-113">[删除收件人](deleting-a-recipient.md)： 介绍如何从可修改容器中删除一个或多个通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="a10a2-113">[Deleting a Recipient](deleting-a-recipient.md): Describes how to remove one or more address book entries from a modifiable container.</span></span>
    
- <span data-ttu-id="a10a2-114">[准备收件人](preparing-a-recipient.md)： 介绍如何通过将其短期条目标识符格式转换为长期条目标识符和可能添加、 更改或重新排序属性准备收件人。</span><span class="sxs-lookup"><span data-stu-id="a10a2-114">[Preparing a Recipient](preparing-a-recipient.md): Describes how to prepares recipients by converting their short-term entry identifiers to long-term entry identifiers and possibly adding, changing, or reordering properties.</span></span>
    
- <span data-ttu-id="a10a2-115">[访问的通讯组列表成员](accessing-the-members-of-a-distribution-list.md)： 介绍如何访问的通讯组列表成员。</span><span class="sxs-lookup"><span data-stu-id="a10a2-115">[Accessing the Members of a Distribution List](accessing-the-members-of-a-distribution-list.md): Describes how to access the members of a distribution list.</span></span>
    
- <span data-ttu-id="a10a2-116">[检索收件人属性](retrieving-recipient-properties.md)： 介绍如何访问收件人地址簿条目的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="a10a2-116">[Retrieving Recipient Properties](retrieving-recipient-properties.md): Describes how to access one or more properties of a recipient address book entry.</span></span>
    
- <span data-ttu-id="a10a2-117">[搜索通讯簿](searching-the-address-book.md)： 描述 MAPI 搜索功能的两个级别。</span><span class="sxs-lookup"><span data-stu-id="a10a2-117">[Searching the Address Book](searching-the-address-book.md): Describes the two levels of MAPI search functionality.</span></span> 
    
- <span data-ttu-id="a10a2-118">[使用高级搜索对话框中](using-an-advanced-search-dialog-box.md)： 介绍如何在通讯簿容器中运行高级的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="a10a2-118">[Using an Advanced Search Dialog Box](using-an-advanced-search-dialog-box.md): Describes how to run an advanced search functionality in an address book container.</span></span>
    
- <span data-ttu-id="a10a2-119">[解析收件人姓名](resolving-a-recipient-name.md)： 介绍了如何解决通讯簿中的名称。</span><span class="sxs-lookup"><span data-stu-id="a10a2-119">[Resolving a Recipient Name](resolving-a-recipient-name.md): Describes how to resolve a name in an address book.</span></span>
    
- <span data-ttu-id="a10a2-120">[展开通讯组列表](expanding-distribution-lists.md)： 介绍如何提示 MAPI 以展开通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a10a2-120">[Expanding Distribution Lists](expanding-distribution-lists.md): Describes how to prompt MAPI to expand a distribution list.</span></span>
    

