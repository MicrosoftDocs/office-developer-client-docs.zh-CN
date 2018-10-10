---
title: 第 15 章：ADOX 基础知识
TOCTitle: 'Chapter 15: ADOX Fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3869f23b93df78fd207812a85f91dd3272bd255f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468584"
---
# <a name="chapter-15-adox-fundamentals"></a><span data-ttu-id="a8951-102">第 15 章：ADOX 基础知识</span><span class="sxs-lookup"><span data-stu-id="a8951-102">Chapter 15: ADOX Fundamentals</span></span>


<span data-ttu-id="a8951-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a8951-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a8951-p101">数据定义语言和安全性 Microsoft® ActiveX® 数据对象扩展 (ADOX) 是对 ADO 对象以及编程模型的扩展。ADOX 包含用于架构创建和修改的对象，以及用于安全性的对象。由于这是一种基于对象的架构处理方法，因此您可以编写可用于各种数据源的代码，而无需考虑这些数据源的特有语法。</span><span class="sxs-lookup"><span data-stu-id="a8951-p101">Microsoft® ActiveX® Data Objects Extensions for Data Definition Language and Security (ADOX) is an extension to the ADO objects and programming model. ADOX includes objects for schema creation and modification, as well as security. Because it is an object-based approach to schema manipulation, you can write code that will work against various data sources regardless of differences in their native syntaxes.</span></span>

<span data-ttu-id="a8951-p102">ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。</span><span class="sxs-lookup"><span data-stu-id="a8951-p102">ADOX is a companion library to the core ADO objects. It exposes additional objects for creating, modifying, and deleting schema objects, such as tables and procedures. It also includes security objects to maintain users and groups and to grant and revoke permissions on objects.</span></span>

<span data-ttu-id="a8951-p103">若要将 ADOX 用于您的开发工具，应建立对 ADOX 类型库的引用。ADOX 库的描述为"Microsoft ADO Ext. for DDL and Security"。ADOX 库的文件名为 Msadox.dll，程序 ID (ProgID) 为"ADOX"。有关如何建立库引用的更多信息，请参阅您的开发工具文档。</span><span class="sxs-lookup"><span data-stu-id="a8951-p103">To use ADOX with your development tool, you should establish a reference to the ADOX type library. The description of the ADOX library is "Microsoft ADO Ext. for DDL and Security." The ADOX library file name is Msadox.dll, and the program ID (ProgID) is "ADOX". For more information about establishing references to libraries, see the documentation of your development tool.</span></span>

<span data-ttu-id="a8951-p104">Microsoft OLE DB Provider for Microsoft Jet Database Engine 完全支持 ADOX。ADOX 的某些功能可能不受支持，这取决于您的数据提供程序。有关 Microsoft OLE DB Provider for ODBC、Microsoft OLE DB Provider for Oracle 或 Microsoft SQL Server OLE DB Provider 支持的功能的更多信息，请参阅 MDAC 自述文件。</span><span class="sxs-lookup"><span data-stu-id="a8951-p104">The Microsoft OLE DB Provider for the Microsoft Jet Database Engine fully supports ADOX. Certain features of ADOX may not be supported, depending on your data provider. For more information about supported features with the Microsoft OLE DB Provider for ODBC, the Microsoft OLE DB Provider for Oracle, or the Microsoft SQL Server OLE DB Provider, see the MDAC readme file.</span></span>

<span data-ttu-id="a8951-p105">本文档需要对 Microsoft® Visual Basic® 编程语言的实用知识以及对 ADO 的一般性了解。有关 ADO 的更多信息，请参阅 [ADO 程序员指南](ado-programmer-s-guide.md)。有关 ADOX 的更多概述信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a8951-p105">This document assumes a working knowledge of the Microsoft® Visual Basic® programming language and a general knowledge of ADO. For more information about ADO, see the [ADO Programmer's Guide](ado-programmer-s-guide.md). For more overview information about ADOX, see the following topics:</span></span>

  - [<span data-ttu-id="a8951-120">ADOX 对象</span><span class="sxs-lookup"><span data-stu-id="a8951-120">ADOX Objects</span></span>](adox-objects.md)

  - [<span data-ttu-id="a8951-121">ADOX 集合</span><span class="sxs-lookup"><span data-stu-id="a8951-121">ADOX Collections</span></span>](adox-collections.md)

  - [<span data-ttu-id="a8951-122">ADOX 属性</span><span class="sxs-lookup"><span data-stu-id="a8951-122">ADOX Properties</span></span>](adox-properties.md)

  - [<span data-ttu-id="a8951-123">ADOX 方法</span><span class="sxs-lookup"><span data-stu-id="a8951-123">ADOX Methods</span></span>](adox-methods.md)

  - [<span data-ttu-id="a8951-124">ADOX 示例</span><span class="sxs-lookup"><span data-stu-id="a8951-124">ADOX Examples</span></span>](adox-code-examples.md)

