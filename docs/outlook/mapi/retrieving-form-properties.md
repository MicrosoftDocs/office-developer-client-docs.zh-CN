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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412917"
---
# <a name="retrieving-form-properties"></a><span data-ttu-id="138c4-103">检索表单属性</span><span class="sxs-lookup"><span data-stu-id="138c4-103">Retrieving Form Properties</span></span>

  
  
<span data-ttu-id="138c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="138c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="138c4-105">若要发出对自定义邮件类型有意义的查询，应用程序需要知道该邮件的预期属性。</span><span class="sxs-lookup"><span data-stu-id="138c4-105">To issue a query that is meaningful to a custom message type, an application needs to know the properties that are expected on that message.</span></span> <span data-ttu-id="138c4-106">若要获取自定义邮件类使用的属性列表，客户端应用程序将查询 MAPI 表单管理器。</span><span class="sxs-lookup"><span data-stu-id="138c4-106">To get a list of properties that a custom message class uses, a client application queries the MAPI form manager.</span></span> <span data-ttu-id="138c4-107">表单管理器从相应的表单配置文件获取此信息，以便客户端应用程序可以使用此信息，而无需开销来激活表单服务器本身。</span><span class="sxs-lookup"><span data-stu-id="138c4-107">The form manager gets this information from the appropriate form configuration file so that client applications can use this information without the overhead of activating the form server itself.</span></span> <span data-ttu-id="138c4-108">为此，客户端应用程序调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md) 方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="138c4-108">To do this, the client application calls the [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method as follows:</span></span> 
  
```cpp
IMAPIFormInfo *pfrminf = NULL;
hr = pfrmmgr->ResolveMessageClass("IPM.Demo", 0L, NULL, &amp;pfrminf);

```

<span data-ttu-id="138c4-109">请注意 **，ResolveMessageClass** 的第三个参数是包含查询将搜索表单服务器的关联内容表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="138c4-109">Note that the third argument to **ResolveMessageClass** is the folder that contains the associated contents table that the query will search for form servers.</span></span> <span data-ttu-id="138c4-110">NULL 指示表单管理器应搜索所有可用的表单容器。</span><span class="sxs-lookup"><span data-stu-id="138c4-110">NULL indicates that the form manager should search all available form containers.</span></span> <span data-ttu-id="138c4-111">如果查询针对特定文件夹运行，最好改为包含相应的 [IMAPIFolder](imapifolderimapicontainer.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="138c4-111">If the query is to run against a particular folder, it is better to include the appropriate [IMAPIFolder](imapifolderimapicontainer.md) pointer instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="138c4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="138c4-112">See also</span></span>



[<span data-ttu-id="138c4-113">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="138c4-113">Form Server Interactions</span></span>](form-server-interactions.md)

