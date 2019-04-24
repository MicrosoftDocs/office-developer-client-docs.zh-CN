---
title: 检索表单属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9dec5ad6-af34-4c5e-848b-5c3909d0c0a1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 023d2cf312438b1e4b6a90c57e1ead7d606d7727
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328649"
---
# <a name="retrieving-form-properties"></a><span data-ttu-id="8a17d-103">检索表单属性</span><span class="sxs-lookup"><span data-stu-id="8a17d-103">Retrieving Form Properties</span></span>

  
  
<span data-ttu-id="8a17d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a17d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a17d-105">若要发出对自定义邮件类型有意义的查询, 应用程序需要知道该邮件上预期的属性。</span><span class="sxs-lookup"><span data-stu-id="8a17d-105">To issue a query that is meaningful to a custom message type, an application needs to know the properties that are expected on that message.</span></span> <span data-ttu-id="8a17d-106">若要获取自定义邮件类使用的属性的列表, 客户端应用程序查询 MAPI 表单管理器。</span><span class="sxs-lookup"><span data-stu-id="8a17d-106">To get a list of properties that a custom message class uses, a client application queries the MAPI form manager.</span></span> <span data-ttu-id="8a17d-107">表单管理器从相应的表单配置文件中获取此信息, 以便客户端应用程序可以使用此信息, 而不会导致激活表单服务器本身的开销。</span><span class="sxs-lookup"><span data-stu-id="8a17d-107">The form manager gets this information from the appropriate form configuration file so that client applications can use this information without the overhead of activating the form server itself.</span></span> <span data-ttu-id="8a17d-108">若要执行此操作, 客户端应用程序将调用[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8a17d-108">To do this, the client application calls the [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method as follows:</span></span> 
  
```cpp
IMAPIFormInfo *pfrminf = NULL;
hr = pfrmmgr->ResolveMessageClass("IPM.Demo", 0L, NULL, &amp;pfrminf);

```

<span data-ttu-id="8a17d-109">请注意, **ResolveMessageClass**的第三个参数是包含查询将在表单服务器中搜索的关联的内容表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8a17d-109">Note that the third argument to **ResolveMessageClass** is the folder that contains the associated contents table that the query will search for form servers.</span></span> <span data-ttu-id="8a17d-110">NULL 表示表单管理器应搜索所有可用的表单容器。</span><span class="sxs-lookup"><span data-stu-id="8a17d-110">NULL indicates that the form manager should search all available form containers.</span></span> <span data-ttu-id="8a17d-111">如果查询要针对特定文件夹运行, 则最好包含相应的[IMAPIFolder](imapifolderimapicontainer.md)指针。</span><span class="sxs-lookup"><span data-stu-id="8a17d-111">If the query is to run against a particular folder, it is better to include the appropriate [IMAPIFolder](imapifolderimapicontainer.md) pointer instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8a17d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a17d-112">See also</span></span>



[<span data-ttu-id="8a17d-113">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="8a17d-113">Form Server Interactions</span></span>](form-server-interactions.md)

