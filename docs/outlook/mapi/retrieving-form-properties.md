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
# <a name="retrieving-form-properties"></a>检索表单属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要发出对自定义邮件类型有意义的查询, 应用程序需要知道该邮件上预期的属性。 若要获取自定义邮件类使用的属性的列表, 客户端应用程序查询 MAPI 表单管理器。 表单管理器从相应的表单配置文件中获取此信息, 以便客户端应用程序可以使用此信息, 而不会导致激活表单服务器本身的开销。 若要执行此操作, 客户端应用程序将调用[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法, 如下所示: 
  
```cpp
IMAPIFormInfo *pfrminf = NULL;
hr = pfrmmgr->ResolveMessageClass("IPM.Demo", 0L, NULL, &amp;pfrminf);

```

请注意, **ResolveMessageClass**的第三个参数是包含查询将在表单服务器中搜索的关联的内容表的文件夹。 NULL 表示表单管理器应搜索所有可用的表单容器。 如果查询要针对特定文件夹运行, 则最好包含相应的[IMAPIFolder](imapifolderimapicontainer.md)指针。 
  
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

