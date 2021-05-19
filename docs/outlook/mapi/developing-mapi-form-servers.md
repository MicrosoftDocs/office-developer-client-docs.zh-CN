---
title: 开发 MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30672a2d-2d39-4292-b21a-97a38485d1de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 63aa9db19c901f47004a7fe52d906846f44b8883
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420764"
---
# <a name="developing-mapi-form-servers"></a>开发 MAPI 表单服务器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本节介绍创建表单服务器可执行文件和表单配置文件以创建自定义 MAPI 表单的过程。 在阅读本节之前，您应熟悉 [MAPI Forms 中的信息](mapi-forms.md)。
  
开发表单服务器包括以下步骤：
  
1. 决定表单将包含哪些信息，并选择一组属性来保存该信息。 有关详细信息，请参阅 [选择窗体的属性集](choosing-a-form-s-property-set.md)。
    
2. 设计用户可与表单属性进行交互的用户界面。
    
3. 选择邮件类，并生成 CLSID (的唯) 。 有关邮件类的概述，请参阅[MAPI Message Classes。](mapi-message-classes.md) 有关邮件类和窗体的信息，请参阅 [选择邮件类](choosing-a-message-class.md)。
    
4. 实现所需的 MAPI 表单接口，以及您的特定表单服务器需要的任何可选接口。 有关详细信息，请参阅编写 [表单服务器代码](writing-form-server-code.md)。 
    
5. 编写用户界面代码以处理用户与表单对象以及表单使用的属性的交互。
    
6. 为表单创建表单配置文件。 有关详细信息，请参阅[File Format of Form Configuration Files。](file-format-of-form-configuration-files.md)
    
7. 在用户计算机上安装表单。 有关详细信息，请参阅 [将窗体安装到库中](installing-a-form-into-a-library.md)。
    
您很可能同时执行步骤 1 到步骤 5，而不是按顺序完成这些步骤。 像许多编程项目一样，开发表单服务器的过程不是一个定义特别明确的顺序的过程。 例如，创建表单配置文件显示为上述第二步，但您可能以增量方式创建表单配置文件，当您向表单服务器添加功能时，该文件将变得更加完整。
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

