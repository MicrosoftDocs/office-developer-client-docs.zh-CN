---
title: 有关 InfoPath XML 互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- msxml 互操作 [infopath 2007]，InfoPath 2007，XML 主互操作程序集、 InfoPath XML 互操作程序集
localization_priority: Normal
ms.assetid: fb28659b-8a71-4f43-9121-2c748fb2c5e1
description: InfoPath XML 互操作程序集提供允许托管的代码和由 Microsoft XML Core Services (MSXML) 公开来自外部应用程序的自动执行 InfoPath COM 服务器之间的互操作性支持。
ms.openlocfilehash: 8d3fb1c1de141fe23c655e82b77d83a8e2b11abd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773860"
---
# <a name="about-the-infopath-xml-interop-assembly"></a>有关 InfoPath XML 互操作程序集

InfoPath XML 互操作程序集提供允许托管的代码和由 Microsoft XML Core Services (MSXML) 公开来自外部应用程序的自动执行 InfoPath COM 服务器之间的互操作性支持。

InfoPath 安装程序中的 **.NET 可编程性支持**选项安装三个互操作程序集。 互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。 这些程序集，Microsoft.Office.Interop.InfoPath.Xml.dll，之一提供用于处理由 COM 服务器公开 Microsoft XML Core Services (MSXML) 的成员的[Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/en-us/library/microsoft.office.interop.infopath.xml)命名空间的成员从外部应用程序的自动执行 InfoPath 托管的代码使用。 
  
> [!NOTE]
> 必须手动建立对 Microsoft.Office.Interop.InfoPath.dll 和 Microsoft.Office.Interop.InfoPath.Xml.dll 互操作程序集所需的 InfoPath 外部自动化项目的引用。 外部自动化的详细信息，请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。 
  
## <a name="see-also"></a>另请参阅

- [使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml](http://msdn.microsoft.com/library/f7a0cac5-26f9-49ed-b52c-0240ef0c9d38%28Office.15%29.aspx)

