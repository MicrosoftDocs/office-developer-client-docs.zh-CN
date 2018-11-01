---
title: 第 14 章：ADO MD 基础知识
TOCTitle: 'Chapter 14: ADO MD Fundamentals'
ms:assetid: 129baa54-0bc1-985d-4bfd-25a1c1c3018e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248899(v=office.15)
ms:contentKeyID: 48543346
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e9e89673dcb5cce124747d914f63d1a38353aebe
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885743"
---
# <a name="chapter-14-ado-md-fundamentals"></a>第 14 章：ADO MD 基础知识


**适用于**： Access 2013、 Office 2013

借助 Microsoft ActiveX 数据对象（多维）(ADO MD)，您可以使用 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 之类的语言轻松访问多维数据。ADO MD 将 Microsoft ActiveX 数据对象 (ADO) 扩展为包括特定于多维数据的对象，如 [CubeDef](cubedef-object-ado-md.md) 和 [Cellset](cellset-object-ado-md.md) 对象。通过 ADO MD，您可以浏览多维架构、查询多维数据集，以及检索结果。

与 ADO 相仿，ADO MD 也使用基础 OLE DB 提供程序来获得对数据的访问。为了使用 ADO MD，您的提供程序必须是 OLE DB for OLAP 规范所定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，与此相对，表格式数据提供程序 (TDP) 则以表格式视图显示数据。有关您的提供程序所支持的特定语法和行为的更多详细信息，请参考您的 OLAP OLE DB 提供程序的文档。

本文档需要具有 Visual Basic 编程语言的实用知识和对 ADO 和 OLAP 的一般性了解。 有关详细信息，请参阅 [ADO 程序员指南](ado-programmer-s-guide.md)以及 OLE DB for OLAP 程序员参考。 

本章包含以下主题：

- [多维架构和数据概述](overview-of-multidimensional-schemas-and-data.md)

- [处理多维数据](working-with-multidimensional-data.md)

- [将 ADO 与 ADO MD 结合使用](using-ado-with-ado-md.md)

- [ADO MD 编程](programming-with-ado-md.md)
