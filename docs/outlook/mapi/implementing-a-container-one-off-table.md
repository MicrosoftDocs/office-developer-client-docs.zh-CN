---
title: 实现容器一次性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eabbde74-49a1-4eeb-a01d-67e45ae4b343
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 83351e18750ccbffbe60c4e19f9b04a9c94a42e2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775778"
---
# <a name="implementing-a-container-one-off-table"></a><span data-ttu-id="f26bc-103">实现容器一次性表</span><span class="sxs-lookup"><span data-stu-id="f26bc-103">Implementing a Container One-Off Table</span></span>

  
  
<span data-ttu-id="f26bc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f26bc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f26bc-105">若要访问一次性表属于您容器之一，MAPI 调用的容器[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IMAPITable**打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性接口。</span><span class="sxs-lookup"><span data-stu-id="f26bc-105">To access the one-off table belonging to one of your containers, MAPI calls the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property with the **IMAPITable** interface.</span></span> <span data-ttu-id="f26bc-106">您的容器要求客户端应用程序尝试将收件人添加到容器时返回其一次性表。</span><span class="sxs-lookup"><span data-stu-id="f26bc-106">Your container is asked to return its one-off table when a client application is trying to add a recipient to the container.</span></span> <span data-ttu-id="f26bc-107">如果容器允许任何收件人，您的提供商可以返回它自己的表实现或呼叫[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)返回 MAPI 实现。</span><span class="sxs-lookup"><span data-stu-id="f26bc-107">If the container allows any recipients, your provider can either return its own table implementation or call [IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md) to return the MAPI implementation.</span></span> 
  
<span data-ttu-id="f26bc-108">容器一次性表中的模板集应反映特定容器可以包含的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="f26bc-108">The set of templates in the container one-off table should reflect the type of recipients that the particular container can hold.</span></span> <span data-ttu-id="f26bc-109">通常，这包括一个或两个模板，用于创建单个邮件用户或通讯组列表的模板。</span><span class="sxs-lookup"><span data-stu-id="f26bc-109">Typically, this includes one or two templates, templates for creating an individual messaging user or a distribution list.</span></span> <span data-ttu-id="f26bc-110">**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性中保留这些模板的项标识符。</span><span class="sxs-lookup"><span data-stu-id="f26bc-110">The entry identifiers for these templates are held in the **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) and **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) properties.</span></span> <span data-ttu-id="f26bc-111">但是，容器不是限制为这些类型的项。</span><span class="sxs-lookup"><span data-stu-id="f26bc-111">However, containers are by no means limited to these types of entries.</span></span> <span data-ttu-id="f26bc-112">它们可以保存其他类型的收件人或非收件人条目，如目录。</span><span class="sxs-lookup"><span data-stu-id="f26bc-112">They can hold other types of recipients or non-recipient entries such as directories.</span></span> 
  

