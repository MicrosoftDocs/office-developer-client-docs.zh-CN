---
title: 关于表单模板组件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: b51361fe-cf29-f890-9876-5aebe15c73e1
description: Microsoft InfoPath 表单模板由结合使用的多个文件和组件组成，它们共同提供特定的功能以满足特定的最终用户方案或业务需求。InfoPath 表单在复杂性方面可能会有所变化，这取决于它们所服务的需求的类型。
ms.openlocfilehash: 3c5adc7ec1e24af481dff7f4a8d009b2dcb6ba8a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303792"
---
# <a name="about-form-template-components"></a>关于表单模板组件

Microsoft InfoPath 表单模板由结合使用的多个文件和组件组成，它们共同提供特定的功能以满足特定的最终用户方案或业务需求。InfoPath 表单在复杂性方面可能会有所变化，这取决于它们所服务的需求的类型。
  
从本质上说，InfoPath 表单模板是一类应用程序，它创建特定类别的 XML 文档，定义其版式和编辑行为，强制其数据一致性，并且提供表明其存储位置的传送信息。
  
了解 InfoPath 表单模板是由属于许多不同类型的几个不同文件组成，这一点很重要；这些文件统称为表单文件。通常，InfoPath 表单模板由下列类型的文件组成。
  
|**名称**|**扩展名**|**说明**|
|:-----|:-----|:-----|
|表单定义  <br/> |.xsf  <br/> |InfoPath 生成的文件，其中包含有关表单中所使用的所有其他文件和组件的信息。该文件作为表单的指令清单。  <br/> |
|XML 架构  <br/> |.xsd  <br/> |XML 架构文件，用于约束和验证表单的基础 XML 文档文件。  <br/> |
|视图  <br/> |.xsl  <br/> |样式表逻辑文件，用于显示、查看和转换表单的基础 XML 文档文件中所包含的数据。  <br/> |
|XML 模板  <br/> |.xml  <br/> |.xml 文件，包含新建表单时显示在视图中的默认数据。  <br/> |
|演示文稿  <br/> |.htm, .gif, .bmp 及其他  <br/> |结合视图文件使用以创建自定义用户界面的文件。  <br/> |
|业务逻辑  <br/> |.dll  <br/> |用于实现特定的编辑行为、数据有效性、事件处理程序、数据流的控制以及其他自定义业务逻辑的已编译编程代码。可以使用 Visual Basic 和 C# .NET 编程语言来编写 InfoPath 业务逻辑，这些语言是经过编译的，并且以二进制文件形式提供。  <br/> |
|二进制组件  <br/> |.dll, .exe  <br/> | 提供附加业务逻辑的任何自定义组件。  <br/> |
|表单模板  <br/> |.xsn  <br/> |将所有表单文件打包成一个文件的压缩文件格式 (.cab)。  <br/> |
   

