---
title: 实现One-Off表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57933d44-d47a-4e7f-ba95-b49b4934d0a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c29feae84d81874988997409fd229b042a701640
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421639"
---
# <a name="implementing-one-off-tables"></a><span data-ttu-id="32ede-103">实现One-Off表</span><span class="sxs-lookup"><span data-stu-id="32ede-103">Implementing One-Off Tables</span></span>

<span data-ttu-id="32ede-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="32ede-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="32ede-105">提供程序可能实现一个或多个一键式表。</span><span class="sxs-lookup"><span data-stu-id="32ede-105">Your provider might implement one or more one-off tables.</span></span> <span data-ttu-id="32ede-106">一对多表是用于创建收件人的一次使用模板的摘要列表，这些模板直接放入容器或传出邮件的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="32ede-106">A one-off table is a summary list of one-off templates used to create recipients, either directly into a container or into the recipient list of an outgoing message.</span></span> <span data-ttu-id="32ede-107">一次使用模板是用户用于输入与特定地址类型相关的数据的表单。</span><span class="sxs-lookup"><span data-stu-id="32ede-107">A one-off template is a form users employ for entering data relevant to a particular type of address.</span></span> <span data-ttu-id="32ede-108">当用户完成对模板的处理后，您的提供程序将创建新收件人并添加到邮件中。</span><span class="sxs-lookup"><span data-stu-id="32ede-108">When the user is finished working with the template, your provider creates the new recipient and adds it to the message.</span></span> <span data-ttu-id="32ede-109">通常，每个模板处理一个地址类型。</span><span class="sxs-lookup"><span data-stu-id="32ede-109">Typically each template handles a single address type.</span></span> <span data-ttu-id="32ede-110">但是，模板可以处理多个类型，也可以让多个模板处理同一类型。</span><span class="sxs-lookup"><span data-stu-id="32ede-110">However, it is possible for a template to handle multiple types or for multiple templates to handle the same type.</span></span> 
  
<span data-ttu-id="32ede-111">您的提供程序必须支持其包括在一次方表中的每个模板的 **OpenEntry** 方法。</span><span class="sxs-lookup"><span data-stu-id="32ede-111">Your provider must support the **OpenEntry** method for each template that it includes in the one-off table.</span></span> <span data-ttu-id="32ede-112">**OpenEntry 的** 实现应检索模板的显示表。</span><span class="sxs-lookup"><span data-stu-id="32ede-112">The implementation of **OpenEntry** should retrieve a display table for the template.</span></span> <span data-ttu-id="32ede-113">MAPI 使用显示表使模板对用户可见。</span><span class="sxs-lookup"><span data-stu-id="32ede-113">MAPI uses the display table to make the template visible to the user.</span></span> 
  
<span data-ttu-id="32ede-114">尽管一键式表中的大多数行表示模板，但某些行可用于对模板进行分类或分组。</span><span class="sxs-lookup"><span data-stu-id="32ede-114">Although most of the rows in one-off tables represent templates, some of the rows can be used to categorize, or group, templates.</span></span> <span data-ttu-id="32ede-115">一次方表中的行是否表示模板由它的 **PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) 指示。</span><span class="sxs-lookup"><span data-stu-id="32ede-115">Whether or not a row in a one-off table represents a template is indicated by the value of its **PR_SELECTABLE** ([PidTagSelectable](pidtagselectable-canonical-property.md)) column.</span></span> <span data-ttu-id="32ede-116">表示模板的行将PR_SELECTABLE设置为 TRUE;不表示模板的行将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="32ede-116">Rows that represent templates have the PR_SELECTABLE column set to TRUE; rows that do not represent templates have it set to FALSE.</span></span>
  
<span data-ttu-id="32ede-117">MAPI 定义三种类型的一键式表：</span><span class="sxs-lookup"><span data-stu-id="32ede-117">MAPI defines three types of one-off tables:</span></span>
  
- <span data-ttu-id="32ede-118">反映单个容器支持的模板的一对一表</span><span class="sxs-lookup"><span data-stu-id="32ede-118">A one-off table that reflects the templates that an individual container supports</span></span>
    
- <span data-ttu-id="32ede-119">反映提供程序支持的所有模板的一对一表</span><span class="sxs-lookup"><span data-stu-id="32ede-119">A one-off table that reflects all of the templates that your provider supports</span></span> 
    
- <span data-ttu-id="32ede-120">反映配置文件中所有提供程序支持的所有模板以及 MAPI 支持的一些模板的一对表</span><span class="sxs-lookup"><span data-stu-id="32ede-120">A one-off table that reflects all of the templates that all of the providers in the profile support plus some that MAPI supports</span></span>
    
<span data-ttu-id="32ede-121">前两种类型由支持创建收件人的提供程序实现，既可以在邮件上实现，也可以支持放入容器中。</span><span class="sxs-lookup"><span data-stu-id="32ede-121">The first two types are implemented by providers that support the creation recipients, either onto a message or into a container.</span></span> <span data-ttu-id="32ede-122">您的提供程序可以在其一键式表中包含同一组模板或另一组模板。</span><span class="sxs-lookup"><span data-stu-id="32ede-122">Your provider can include the same set or a different set of templates in its one-off tables.</span></span> <span data-ttu-id="32ede-123">这两种类型之间的主要区别在于，您的提供程序表应包含用于创建可在传出邮件中使用的收件人的模板，而容器表应包含用于创建要添加到容器的收件人的模板。</span><span class="sxs-lookup"><span data-stu-id="32ede-123">The main difference between the two types is that your provider table should include templates for creating recipients that can be used on outgoing messages and your container table should include templates for creating recipients to be added to your container.</span></span> <span data-ttu-id="32ede-124">容器可能仅支持一组受限制的模板，但提供程序一次表应包含提供程序支持的每一个模板。</span><span class="sxs-lookup"><span data-stu-id="32ede-124">A container may only support a restricted set of templates, but the provider one-off table should include every template the provider supports.</span></span>
  
<span data-ttu-id="32ede-125">第三种类型的一对一表由 MAPI 实现;提供程序通过调用 [IMAPISupport：：GetOneOffTable 获取对它的访问](imapisupport-getoneofftable.md)权。</span><span class="sxs-lookup"><span data-stu-id="32ede-125">The third type of one-off table is implemented by MAPI; providers gain access to it by calling [IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md).</span></span> <span data-ttu-id="32ede-126">MAPI 一键式表是所有提供程序表的并列;它包括配置文件中每个提供程序支持的每一个模板。</span><span class="sxs-lookup"><span data-stu-id="32ede-126">The MAPI one-off table is the union of all of the provider tables; it includes every template supported by every provider in the profile.</span></span> <span data-ttu-id="32ede-127">它还包括 MAPI 支持的模板。</span><span class="sxs-lookup"><span data-stu-id="32ede-127">It also includes templates supported by MAPI.</span></span> <span data-ttu-id="32ede-128">提供程序可以使用此表来表示容器请求的表。</span><span class="sxs-lookup"><span data-stu-id="32ede-128">Your provider can use this table in place of the table requested for a container.</span></span> <span data-ttu-id="32ede-129">但是，此表中的模板还可用于为传出邮件创建收件人。</span><span class="sxs-lookup"><span data-stu-id="32ede-129">However, the templates in this table can also be used for creating recipients for outgoing messages.</span></span>
  

