---
title: 开发 MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30672a2d-2d39-4292-b21a-97a38485d1de
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d55134cf5181ebbba0108c228d9afc3a494e75ce
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576237"
---
# <a name="developing-mapi-form-servers"></a>开发 MAPI 表单服务器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本节介绍创建窗体服务器可执行文件和用于创建自定义 MAPI 窗体的窗体配置文件的过程。 在之前阅读本节，您应熟悉[MAPI 窗体](mapi-forms.md)中的信息。
  
开发表单服务器包括以下步骤：
  
1. 确定窗体将包含哪些信息，然后选择要保留的信息的属性集。 有关详细信息，请参阅[Choosing 窗体的属性设置](choosing-a-form-s-property-set.md)。
    
2. 设计与，用户可以与窗体的属性进行交互的用户界面。
    
3. 选择邮件类并生成的唯一的类标识符 (CLSID)。 邮件类的概述，请参阅[MAPI 邮件类](mapi-message-classes.md)。 有关邮件类和窗体的详细信息，请参阅[Choosing 邮件类](choosing-a-message-class.md)。
    
4. 实现所需的 MAPI 表单接口，以及特定窗体服务器需要的任何可选接口。 有关详细信息，请参阅[编写窗体服务器代码](writing-form-server-code.md)。 
    
5. 编写用户界面的代码来处理用户交互的 form 对象和属性使用窗体。
    
6. 创建窗体的窗体配置文件。 有关详细信息，请参阅[窗体配置文件的文件格式](file-format-of-form-configuration-files.md)。
    
7. 用户的计算机上安装窗体。 有关详细信息，请参阅[安装到库窗体](installing-a-form-into-a-library.md)。
    
您很可能将执行步骤 1 至 5 同时而不是从顺序完成它们。 开发一个窗体服务器，许多编程项目，如过程不是一个处于特别是定义完善序列。 例如，创建窗体配置文件显示为第二个上次步骤，您可能将创建窗体配置文件增量，但它将变得更完整，您将功能添加到窗体服务器。
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

