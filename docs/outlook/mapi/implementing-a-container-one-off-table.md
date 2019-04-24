---
title: 实现容器一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eabbde74-49a1-4eeb-a01d-67e45ae4b343
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72dc73b6ed8519be2d8010544fdd5dc5b7b0f759
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332884"
---
# <a name="implementing-a-container-one-off-table"></a><span data-ttu-id="d7682-103">实现容器一次性表</span><span class="sxs-lookup"><span data-stu-id="d7682-103">Implementing a Container One-Off Table</span></span>

  
  
<span data-ttu-id="d7682-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7682-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7682-105">若要访问属于某个容器的一次性表, MAPI 会调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 以使用**IMAPITable**打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性交互.</span><span class="sxs-lookup"><span data-stu-id="d7682-105">To access the one-off table belonging to one of your containers, MAPI calls the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property with the **IMAPITable** interface.</span></span> <span data-ttu-id="d7682-106">当客户端应用程序尝试向容器中添加收件人时, 将要求您的容器返回其一次性表格。</span><span class="sxs-lookup"><span data-stu-id="d7682-106">Your container is asked to return its one-off table when a client application is trying to add a recipient to the container.</span></span> <span data-ttu-id="d7682-107">如果容器允许任何收件人, 则提供程序可以返回自己的表实现或调用[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)以返回 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="d7682-107">If the container allows any recipients, your provider can either return its own table implementation or call [IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md) to return the MAPI implementation.</span></span> 
  
<span data-ttu-id="d7682-108">容器一次性表中的一组模板应反映特定容器可以包含的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="d7682-108">The set of templates in the container one-off table should reflect the type of recipients that the particular container can hold.</span></span> <span data-ttu-id="d7682-109">通常情况下, 这包括一个或两个模板, 这些模板用于创建单个邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d7682-109">Typically, this includes one or two templates, templates for creating an individual messaging user or a distribution list.</span></span> <span data-ttu-id="d7682-110">这些模板的条目标识符保存在**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="d7682-110">The entry identifiers for these templates are held in the **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) and **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) properties.</span></span> <span data-ttu-id="d7682-111">但是, 容器的含义并不局限于这些类型的条目。</span><span class="sxs-lookup"><span data-stu-id="d7682-111">However, containers are by no means limited to these types of entries.</span></span> <span data-ttu-id="d7682-112">他们可以保留其他类型的收件人或非收件人条目 (如目录)。</span><span class="sxs-lookup"><span data-stu-id="d7682-112">They can hold other types of recipients or non-recipient entries such as directories.</span></span> 
  

