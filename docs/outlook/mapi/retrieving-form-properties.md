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
# <a name="retrieving-form-properties"></a>检索表单属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要发出对自定义邮件类型有意义的查询，应用程序需要知道该邮件的预期属性。 若要获取自定义邮件类使用的属性列表，客户端应用程序将查询 MAPI 表单管理器。 表单管理器从相应的表单配置文件获取此信息，以便客户端应用程序可以使用此信息，而无需开销来激活表单服务器本身。 为此，客户端应用程序调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md) 方法，如下所示： 
  
```cpp
IMAPIFormInfo *pfrminf = NULL;
hr = pfrmmgr->ResolveMessageClass("IPM.Demo", 0L, NULL, &amp;pfrminf);

```

请注意 **，ResolveMessageClass** 的第三个参数是包含查询将搜索表单服务器的关联内容表的文件夹。 NULL 指示表单管理器应搜索所有可用的表单容器。 如果查询针对特定文件夹运行，最好改为包含相应的 [IMAPIFolder](imapifolderimapicontainer.md) 指针。 
  
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

