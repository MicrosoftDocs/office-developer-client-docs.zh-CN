---
title: 实现一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57933d44-d47a-4e7f-ba95-b49b4934d0a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c29feae84d81874988997409fd229b042a701640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310127"
---
# <a name="implementing-one-off-tables"></a><span data-ttu-id="5a563-103">实现一次性表</span><span class="sxs-lookup"><span data-stu-id="5a563-103">Implementing One-Off Tables</span></span>

<span data-ttu-id="5a563-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5a563-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5a563-105">提供程序可以实现一个或多个一次性表。</span><span class="sxs-lookup"><span data-stu-id="5a563-105">Your provider might implement one or more one-off tables.</span></span> <span data-ttu-id="5a563-106">一次性表格是用于创建收件人的一次性模板的摘要列表, 这些模板可直接指向容器或传出邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="5a563-106">A one-off table is a summary list of one-off templates used to create recipients, either directly into a container or into the recipient list of an outgoing message.</span></span> <span data-ttu-id="5a563-107">一次性模板是用户在输入与特定地址类型相关的数据时使用的表单。</span><span class="sxs-lookup"><span data-stu-id="5a563-107">A one-off template is a form users employ for entering data relevant to a particular type of address.</span></span> <span data-ttu-id="5a563-108">在用户使用完模板后, 提供程序将创建新的收件人并将其添加到邮件中。</span><span class="sxs-lookup"><span data-stu-id="5a563-108">When the user is finished working with the template, your provider creates the new recipient and adds it to the message.</span></span> <span data-ttu-id="5a563-109">通常, 每个模板都处理一个地址类型。</span><span class="sxs-lookup"><span data-stu-id="5a563-109">Typically each template handles a single address type.</span></span> <span data-ttu-id="5a563-110">但是, 模板可以处理多个类型或多个模板来处理同一类型。</span><span class="sxs-lookup"><span data-stu-id="5a563-110">However, it is possible for a template to handle multiple types or for multiple templates to handle the same type.</span></span> 
  
<span data-ttu-id="5a563-111">提供程序必须支持它包含在一次性表中的每个模板的**OpenEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="5a563-111">Your provider must support the **OpenEntry** method for each template that it includes in the one-off table.</span></span> <span data-ttu-id="5a563-112">**OpenEntry**的实现应检索模板的显示表。</span><span class="sxs-lookup"><span data-stu-id="5a563-112">The implementation of **OpenEntry** should retrieve a display table for the template.</span></span> <span data-ttu-id="5a563-113">MAPI 使用显示表格使该模板对用户可见。</span><span class="sxs-lookup"><span data-stu-id="5a563-113">MAPI uses the display table to make the template visible to the user.</span></span> 
  
<span data-ttu-id="5a563-114">虽然一次性表中的大多数行都代表模板, 但某些行可用于对模板进行分类或分组。</span><span class="sxs-lookup"><span data-stu-id="5a563-114">Although most of the rows in one-off tables represent templates, some of the rows can be used to categorize, or group, templates.</span></span> <span data-ttu-id="5a563-115">一次性表中的行是否表示模板由其**PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 列的值指示。</span><span class="sxs-lookup"><span data-stu-id="5a563-115">Whether or not a row in a one-off table represents a template is indicated by the value of its **PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) column.</span></span> <span data-ttu-id="5a563-116">表示模板的行的 "PR_SELECTABLE" 列设置为 TRUE;不表示模板的行已将其设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="5a563-116">Rows that represent templates have the PR_SELECTABLE column set to TRUE; rows that do not represent templates have it set to FALSE.</span></span>
  
<span data-ttu-id="5a563-117">MAPI 定义了三种类型的一次性表:</span><span class="sxs-lookup"><span data-stu-id="5a563-117">MAPI defines three types of one-off tables:</span></span>
  
- <span data-ttu-id="5a563-118">反映单个容器支持的模板的一次性表</span><span class="sxs-lookup"><span data-stu-id="5a563-118">A one-off table that reflects the templates that an individual container supports</span></span>
    
- <span data-ttu-id="5a563-119">反映提供程序支持的所有模板的一次性表</span><span class="sxs-lookup"><span data-stu-id="5a563-119">A one-off table that reflects all of the templates that your provider supports</span></span> 
    
- <span data-ttu-id="5a563-120">一个一次性表, 反映配置文件支持中的所有提供程序和 MAPI 支持的所有模板</span><span class="sxs-lookup"><span data-stu-id="5a563-120">A one-off table that reflects all of the templates that all of the providers in the profile support plus some that MAPI supports</span></span>
    
<span data-ttu-id="5a563-121">前两种类型由支持创建收件人的提供程序实现, 无论是在邮件上, 还是在容器中。</span><span class="sxs-lookup"><span data-stu-id="5a563-121">The first two types are implemented by providers that support the creation recipients, either onto a message or into a container.</span></span> <span data-ttu-id="5a563-122">提供程序可以在其一次性表中包含相同的一组或一组不同的模板。</span><span class="sxs-lookup"><span data-stu-id="5a563-122">Your provider can include the same set or a different set of templates in its one-off tables.</span></span> <span data-ttu-id="5a563-123">这两种类型的主要区别在于, 提供程序表应包含用于创建可用于传出邮件的收件人的模板, 并且您的容器表应包含用于创建要添加到容器中的收件人的模板。</span><span class="sxs-lookup"><span data-stu-id="5a563-123">The main difference between the two types is that your provider table should include templates for creating recipients that can be used on outgoing messages and your container table should include templates for creating recipients to be added to your container.</span></span> <span data-ttu-id="5a563-124">容器仅支持一组有限的模板, 但提供程序的一次性表应包含提供程序支持的每个模板。</span><span class="sxs-lookup"><span data-stu-id="5a563-124">A container may only support a restricted set of templates, but the provider one-off table should include every template the provider supports.</span></span>
  
<span data-ttu-id="5a563-125">第三种类型的一次性表是由 MAPI 实现的;提供程序通过调用[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)获取对它的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5a563-125">The third type of one-off table is implemented by MAPI; providers gain access to it by calling [IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md).</span></span> <span data-ttu-id="5a563-126">MAPI 一次性表是所有提供程序表的并集;它包括配置文件中每个提供程序支持的每个模板。</span><span class="sxs-lookup"><span data-stu-id="5a563-126">The MAPI one-off table is the union of all of the provider tables; it includes every template supported by every provider in the profile.</span></span> <span data-ttu-id="5a563-127">它还包括 MAPI 支持的模板。</span><span class="sxs-lookup"><span data-stu-id="5a563-127">It also includes templates supported by MAPI.</span></span> <span data-ttu-id="5a563-128">提供程序可以使用此表代替为容器请求的表。</span><span class="sxs-lookup"><span data-stu-id="5a563-128">Your provider can use this table in place of the table requested for a container.</span></span> <span data-ttu-id="5a563-129">但是, 此表中的模板还可用于创建传出邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="5a563-129">However, the templates in this table can also be used for creating recipients for outgoing messages.</span></span>
  

