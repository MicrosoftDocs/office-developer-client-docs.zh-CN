---
title: 检索表单属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9dec5ad6-af34-4c5e-848b-5c3909d0c0a1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 334ecaacec88c3730f4cc2f4c80eb35d5a553c4e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778647"
---
# <a name="retrieving-form-properties"></a>检索表单属性

  
  
**适用于**： Outlook 
  
发出查询的自定义消息类型有意义，应用程序需要知道预期邮件的属性。 若要获取的自定义邮件类别所使用的属性的列表，客户端应用程序查询 MAPI 窗体管理器。 窗体管理器从相应的窗体配置文件中获取此信息，以便客户端应用程序可以使用无需开销激活窗体服务器本身的此信息。 若要执行此操作，客户端应用程序调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法，如下所示： 
  
```cpp
IMAPIFormInfo *pfrminf = NULL;
hr = pfrmmgr->ResolveMessageClass("IPM.Demo", 0L, NULL, &amp;pfrminf);

```

请注意到**ResolveMessageClass**第三个参数是包含查询将搜索表单服务器的关联的内容表的文件夹。 NULL 指示窗体管理器应搜索所有可用表单容器。 如果查询针对特定文件夹运行，则最好改为包括将适当的[IMAPIFolder](imapifolderimapicontainer.md)指针。 
  
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

