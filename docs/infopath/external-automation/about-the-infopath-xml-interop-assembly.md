---
title: 关于 InfoPath XML 互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- msxml interop [infopath 2007]，InfoPath 2007， XML 主互操作程序集，InfoPath XML 互操作程序集
localization_priority: Normal
ms.assetid: fb28659b-8a71-4f43-9121-2c748fb2c5e1
description: InfoPath XML 互操作程序集用于支持托管代码与由自动执行 InfoPath 的外部Microsoft XML Core Services (MSXML)  (MSXML) 公开的 COM 服务器之间的互操作性。
ms.openlocfilehash: 8d47fb58c5133fa14ac78aa8fb29278b70c26abb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303778"
---
# <a name="about-the-infopath-xml-interop-assembly"></a>关于 InfoPath XML 互操作程序集

InfoPath XML 互操作程序集用于支持托管代码与由自动执行 InfoPath 的外部Microsoft XML Core Services (MSXML)  (MSXML) 公开的 COM 服务器之间的互操作性。

InfoPath **安装程序中的 .NET 可编程** 性支持选项将安装三个互操作程序集。 互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。 其中一个程序集 Microsoft.Office.Interop.InfoPath.Xml.dll 提供[Microsoft.Office.Interop.InfoPath.Xml](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.infopath.xml?view=infopath-external)命名空间的成员，该命名空间用于处理 COM 服务器针对 Microsoft XML Core Services (MSXML)  (MSXML) 公开的成员，这些成员来自使用托管代码自动化 InfoPath 的外部应用程序。 
  
> [!NOTE]
> 必须手动建立Microsoft.Office.Interop.InfoPath.dll InfoPath Microsoft.Office.Interop.InfoPath.Xml.dll项目所需的内部互操作程序集和互操作程序集的引用。 有关外部自动化详细信息，请参阅外部 [自动化方案和示例](external-automation-scenarios-and-examples.md)。 
  
## <a name="see-also"></a>另请参阅

- [使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml](https://msdn.microsoft.com/library/f7a0cac5-26f9-49ed-b52c-0240ef0c9d38%28Office.15%29.aspx)

