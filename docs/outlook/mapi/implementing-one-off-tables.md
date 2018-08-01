---
title: 实现一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57933d44-d47a-4e7f-ba95-b49b4934d0a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b72b8658270a8e007123df3ead01168208b8d1b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775807"
---
# <a name="implementing-one-off-tables"></a><span data-ttu-id="64e96-103">实现一次性表</span><span class="sxs-lookup"><span data-stu-id="64e96-103">Implementing One-Off Tables</span></span>

<span data-ttu-id="64e96-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="64e96-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="64e96-105">您的提供商可能实现一个或多个一次性表。</span><span class="sxs-lookup"><span data-stu-id="64e96-105">Your provider might implement one or more one-off tables.</span></span> <span data-ttu-id="64e96-106">一次性表是一次性模板用于创建收件人，直接将容器或到收件人列表中的传出邮件的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="64e96-106">A one-off table is a summary list of one-off templates used to create recipients, either directly into a container or into the recipient list of an outgoing message.</span></span> <span data-ttu-id="64e96-107">一次性模板是地址的输入与特定类型相关的数据表单用户使用。</span><span class="sxs-lookup"><span data-stu-id="64e96-107">A one-off template is a form users employ for entering data relevant to a particular type of address.</span></span> <span data-ttu-id="64e96-108">用户已完成时使用的模板，您的提供程序创建新收件人并将其添加到邮件。</span><span class="sxs-lookup"><span data-stu-id="64e96-108">When the user is finished working with the template, your provider creates the new recipient and adds it to the message.</span></span> <span data-ttu-id="64e96-109">通常，每个模板处理单个地址类型。</span><span class="sxs-lookup"><span data-stu-id="64e96-109">Typically each template handles a single address type.</span></span> <span data-ttu-id="64e96-110">但是，也可能模板可以处理多个类型或多个要处理的相同类型的模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-110">However, it is possible for a template to handle multiple types or for multiple templates to handle the same type.</span></span> 
  
<span data-ttu-id="64e96-111">您的提供商必须支持它包括一次性表中的每个模板**OpenEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="64e96-111">Your provider must support the **OpenEntry** method for each template that it includes in the one-off table.</span></span> <span data-ttu-id="64e96-112">**OpenEntry**的实现应检索显示表格模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-112">The implementation of **OpenEntry** should retrieve a display table for the template.</span></span> <span data-ttu-id="64e96-113">MAPI 使用显示表以使该模板对用户可见。</span><span class="sxs-lookup"><span data-stu-id="64e96-113">MAPI uses the display table to make the template visible to the user.</span></span> 
  
<span data-ttu-id="64e96-114">虽然大部分一次性表中的行代表模板，但某些行可用于分类，或组，模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-114">Although most of the rows in one-off tables represent templates, some of the rows can be used to categorize, or group, templates.</span></span> <span data-ttu-id="64e96-115">一次性表中的行代表由其**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 列的值指示模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-115">Whether or not a row in a one-off table represents a template is indicated by the value of its **PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) column.</span></span> <span data-ttu-id="64e96-116">代表模板的各行都设置为 TRUE; 的 PR_SELECTABLE 栏行不表示模板已设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="64e96-116">Rows that represent templates have the PR_SELECTABLE column set to TRUE; rows that do not represent templates have it set to FALSE.</span></span>
  
<span data-ttu-id="64e96-117">MAPI 定义三种类型的一次性表：</span><span class="sxs-lookup"><span data-stu-id="64e96-117">MAPI defines three types of one-off tables:</span></span>
  
- <span data-ttu-id="64e96-118">一个一次性表，反映了单个容器所支持的模板</span><span class="sxs-lookup"><span data-stu-id="64e96-118">A one-off table that reflects the templates that an individual container supports</span></span>
    
- <span data-ttu-id="64e96-119">反映您的提供商支持的模板的所有一次性表</span><span class="sxs-lookup"><span data-stu-id="64e96-119">A one-off table that reflects all of the templates that your provider supports</span></span> 
    
- <span data-ttu-id="64e96-120">一个一次性表，反映的所有模板的所有配置文件中提供程序支持 plus 某些的 MAPI 支持</span><span class="sxs-lookup"><span data-stu-id="64e96-120">A one-off table that reflects all of the templates that all of the providers in the profile support plus some that MAPI supports</span></span>
    
<span data-ttu-id="64e96-121">由提供程序支持创建收件人，到一条消息，或到容器实现的前两个的类型。</span><span class="sxs-lookup"><span data-stu-id="64e96-121">The first two types are implemented by providers that support the creation recipients, either onto a message or into a container.</span></span> <span data-ttu-id="64e96-122">您的提供商可以包含一组相同或不同的模板集及其一次性表中。</span><span class="sxs-lookup"><span data-stu-id="64e96-122">Your provider can include the same set or a different set of templates in its one-off tables.</span></span> <span data-ttu-id="64e96-123">两种类型的主要区别是提供程序表应包含模板，用于创建可用于待发邮件的收件人和容器表应包含模板，用于创建收件人添加到您的容器。</span><span class="sxs-lookup"><span data-stu-id="64e96-123">The main difference between the two types is that your provider table should include templates for creating recipients that can be used on outgoing messages and your container table should include templates for creating recipients to be added to your container.</span></span> <span data-ttu-id="64e96-124">容器可能仅支持一组有限的模板，但提供程序一次性表应包含每个模板提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="64e96-124">A container may only support a restricted set of templates, but the provider one-off table should include every template the provider supports.</span></span>
  
<span data-ttu-id="64e96-125">MAPI; 由实现一次性表的第三种类型提供对其进行访问通过调用[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)。</span><span class="sxs-lookup"><span data-stu-id="64e96-125">The third type of one-off table is implemented by MAPI; providers gain access to it by calling [IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md).</span></span> <span data-ttu-id="64e96-126">MAPI 一次性表是全都的提供程序表中。它包括配置文件中的每个提供程序支持的每个模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-126">The MAPI one-off table is the union of all of the provider tables; it includes every template supported by every provider in the profile.</span></span> <span data-ttu-id="64e96-127">它还包括支持 MAPI 的模板。</span><span class="sxs-lookup"><span data-stu-id="64e96-127">It also includes templates supported by MAPI.</span></span> <span data-ttu-id="64e96-128">您的提供商可以使用此替换为容器请求的表的表。</span><span class="sxs-lookup"><span data-stu-id="64e96-128">Your provider can use this table in place of the table requested for a container.</span></span> <span data-ttu-id="64e96-129">但是，此表中的模板还可用于创建待发邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="64e96-129">However, the templates in this table can also be used for creating recipients for outgoing messages.</span></span>
  

