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
  
本节介绍创建表单服务器可执行文件和表单配置文件以创建自定义 MAPI 表单的过程。 阅读本节之前, 应熟悉[MAPI 表单](mapi-forms.md)中的信息。
  
开发表单服务器包括以下步骤:
  
1. 确定表单将包含的信息, 并选择一组用于保存该信息的属性。 有关详细信息, 请参阅[选择表单的属性集](choosing-a-form-s-property-set.md)。
    
2. 设计用户可与表单的属性进行交互的用户界面。
    
3. 选择邮件类别并生成唯一的类标识符 (CLSID)。 有关邮件类别的概述, 请参阅[MAPI 邮件类别](mapi-message-classes.md)。 有关邮件类别和窗体的详细信息, 请参阅[选择邮件类别](choosing-a-message-class.md)。
    
4. 实现所需的 MAPI 表单接口, 以及特定表单服务器所需的任何可选接口。 有关详细信息, 请参阅[编写表单服务器代码](writing-form-server-code.md)。 
    
5. 编写用户界面代码, 以处理用户与表单对象和表单使用的属性的交互。
    
6. 为窗体创建窗体配置文件。 有关详细信息, 请参阅[表单配置文件的文件格式](file-format-of-form-configuration-files.md)。
    
7. 在用户的计算机上安装表单。 有关详细信息, 请参阅将[表单安装到库](installing-a-form-into-a-library.md)中。
    
您很可能会同时执行步骤1到 5, 而不是按顺序完成这些步骤。 开发表单服务器的过程 (如许多编程项目) 不是在其中有一个特别定义明确的序列的过程。 例如, 创建一个窗体配置文件时, 将显示为上面的倒数第二步, 但您可能会以增量方式创建表单配置文件, 在您向表单服务器添加功能时, 该文件将会变得更完整。
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

