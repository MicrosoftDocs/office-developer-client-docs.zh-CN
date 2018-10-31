---
title: 第 14 章：ADO MD 基础知识
TOCTitle: 'Chapter 14: ADO MD Fundamentals'
ms:assetid: 129baa54-0bc1-985d-4bfd-25a1c1c3018e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248899(v=office.15)
ms:contentKeyID: 48543346
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b8576d2a1d579de306b438f7b0fb04a1eb2d46cc
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863636"
---
# <a name="chapter-14-ado-md-fundamentals"></a><span data-ttu-id="d424d-102">第 14 章：ADO MD 基础知识</span><span class="sxs-lookup"><span data-stu-id="d424d-102">Chapter 14: ADO MD Fundamentals</span></span>


<span data-ttu-id="d424d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d424d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d424d-p101">借助 Microsoft ActiveX 数据对象（多维）(ADO MD)，您可以使用 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 之类的语言轻松访问多维数据。ADO MD 将 Microsoft ActiveX 数据对象 (ADO) 扩展为包括特定于多维数据的对象，如 [CubeDef](cubedef-object-ado-md.md) 和 [Cellset](cellset-object-ado-md.md) 对象。通过 ADO MD，您可以浏览多维架构、查询多维数据集，以及检索结果。</span><span class="sxs-lookup"><span data-stu-id="d424d-p101">Microsoft ActiveX Data Objects (Multidimensional) (ADO MD) provides easy access to multidimensional data from languages such as Microsoft Visual Basic, Microsoft Visual C++, and Microsoft Visual J++. ADO MD extends Microsoft ActiveX Data Objects (ADO) to include objects specific to multidimensional data, such as the [CubeDef](cubedef-object-ado-md.md) and [Cellset](cellset-object-ado-md.md) objects. With ADO MD you can browse multidimensional schema, query a cube, and retrieve the results.</span></span>

<span data-ttu-id="d424d-p102">与 ADO 相仿，ADO MD 也使用基础 OLE DB 提供程序来获得对数据的访问。为了使用 ADO MD，您的提供程序必须是 OLE DB for OLAP 规范所定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，与此相对，表格式数据提供程序 (TDP) 则以表格式视图显示数据。有关您的提供程序所支持的特定语法和行为的更多详细信息，请参考您的 OLAP OLE DB 提供程序的文档。</span><span class="sxs-lookup"><span data-stu-id="d424d-p102">Like ADO, ADO MD uses an underlying OLE DB provider to gain access to data. To work with ADO MD, the provider must be a multidimensional data provider (MDP) as defined by the OLE DB for OLAP specification. MDPs present data in multidimensional views as opposed to tabular data providers (TDPs) that present data in tabular views. Refer to the documentation for your OLAP OLE DB provider for more detailed information on the specific syntax and behaviors supported by your provider.</span></span>

<span data-ttu-id="d424d-111">本文档需要具有 Visual Basic 编程语言的实用知识和对 ADO 和 OLAP 的一般性了解。</span><span class="sxs-lookup"><span data-stu-id="d424d-111">This document assumes a working knowledge of the Visual Basic programming language and a general knowledge of ADO and OLAP.</span></span> <span data-ttu-id="d424d-112">有关详细信息，请参阅 [ADO 程序员指南](ado-programmer-s-guide.md)以及 OLE DB for OLAP 程序员参考。</span><span class="sxs-lookup"><span data-stu-id="d424d-112">For more information, see the [ADO Programmer's Guide](ado-programmer-s-guide.md) and the OLE DB for OLAP Programmer's Reference.</span></span> 

<span data-ttu-id="d424d-113">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="d424d-113">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="d424d-114">多维架构和数据概述</span><span class="sxs-lookup"><span data-stu-id="d424d-114">Overview of Multidimensional Schemas and Data</span></span>](overview-of-multidimensional-schemas-and-data.md)

- [<span data-ttu-id="d424d-115">处理多维数据</span><span class="sxs-lookup"><span data-stu-id="d424d-115">Working with Multidimensional Data</span></span>](working-with-multidimensional-data.md)

- [<span data-ttu-id="d424d-116">将 ADO 与 ADO MD 结合使用</span><span class="sxs-lookup"><span data-stu-id="d424d-116">Using ADO with ADO MD</span></span>](using-ado-with-ado-md.md)

- [<span data-ttu-id="d424d-117">ADO MD 编程</span><span class="sxs-lookup"><span data-stu-id="d424d-117">Programming with ADO MD</span></span>](programming-with-ado-md.md)
