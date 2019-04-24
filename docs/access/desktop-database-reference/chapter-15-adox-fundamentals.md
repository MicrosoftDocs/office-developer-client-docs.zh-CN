---
title: 第 15 章：ADOX 基础知识
TOCTitle: 'Chapter 15: ADOX fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0e46920ba47dba018944768ff61c970781e37a02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296449"
---
# <a name="chapter-15-adox-fundamentals"></a><span data-ttu-id="e291d-102">第 15 章：ADOX 基础知识</span><span class="sxs-lookup"><span data-stu-id="e291d-102">Chapter 15: ADOX fundamentals</span></span>

<span data-ttu-id="e291d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e291d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e291d-p101">用于数据定义语言和安全性的 Microsoft ActiveX 数据对象扩展 (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及安全性的对象。由于它基于对象来实现对架构的操控，因此您可以编写代码来处理各类数据源，而无需考虑数据源本来的语法之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e291d-p101">Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) is an extension to the ADO objects and programming model. ADOX includes objects for schema creation and modification, as well as security. Because it is an object-based approach to schema manipulation, you can write code that will work against various data sources regardless of differences in their native syntaxes.</span></span>

<span data-ttu-id="e291d-p102">ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。</span><span class="sxs-lookup"><span data-stu-id="e291d-p102">ADOX is a companion library to the core ADO objects. It exposes additional objects for creating, modifying, and deleting schema objects, such as tables and procedures. It also includes security objects to maintain users and groups and to grant and revoke permissions on objects.</span></span>

<span data-ttu-id="e291d-p103">若要将 ADOX 用于您的开发工具，应建立对 ADOX 类型库的引用。ADOX 库的描述为"Microsoft ADO Ext. for DDL and Security"。ADOX 库的文件名为 Msadox.dll，程序 ID (ProgID) 为"ADOX"。有关如何建立库引用的更多信息，请参阅您的开发工具文档。</span><span class="sxs-lookup"><span data-stu-id="e291d-p103">To use ADOX with your development tool, you should establish a reference to the ADOX type library. The description of the ADOX library is "Microsoft ADO Ext. for DDL and Security." The ADOX library file name is Msadox.dll, and the program ID (ProgID) is "ADOX". For more information about establishing references to libraries, see the documentation of your development tool.</span></span>

<span data-ttu-id="e291d-p104">Microsoft OLE DB Provider for Microsoft Jet Database Engine 完全支持 ADOX。ADOX 的某些功能可能不受支持，这取决于您的数据提供程序。有关 Microsoft OLE DB Provider for ODBC、Microsoft OLE DB Provider for Oracle 或 Microsoft SQL Server OLE DB Provider 支持的功能的更多信息，请参阅 MDAC 自述文件。</span><span class="sxs-lookup"><span data-stu-id="e291d-p104">The Microsoft OLE DB Provider for the Microsoft Jet Database Engine fully supports ADOX. Certain features of ADOX may not be supported, depending on your data provider. For more information about supported features with the Microsoft OLE DB Provider for ODBC, the Microsoft OLE DB Provider for Oracle, or the Microsoft SQL Server OLE DB Provider, see the MDAC readme file.</span></span>

<span data-ttu-id="e291d-117">本文档假定使用 Microsoft Visual Basic 编程语言的相关知识和有关 ADO 的一般性知识。</span><span class="sxs-lookup"><span data-stu-id="e291d-117">This document assumes a working knowledge of the Microsoft Visual Basic programming language and a general knowledge of ADO.</span></span> <span data-ttu-id="e291d-118">有关 ado 的详细信息, 请参阅《 [ado 程序员指南》](ado-programmer-s-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="e291d-118">For more information about ADO, see the [ADO programmer's guide](ado-programmer-s-guide.md).</span></span>

<span data-ttu-id="e291d-119">本章包含以下主题:</span><span class="sxs-lookup"><span data-stu-id="e291d-119">This chapter covers the following topic:</span></span>

- [<span data-ttu-id="e291d-120">ADOX 的提供程序支持</span><span class="sxs-lookup"><span data-stu-id="e291d-120">Provider support for ADOX</span></span>](provider-support-for-adox.md)

<span data-ttu-id="e291d-121">有关 ADOX 的更多概述信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e291d-121">For more overview information about ADOX, see the following topics:</span></span>

- [<span data-ttu-id="e291d-122">ADOX 对象</span><span class="sxs-lookup"><span data-stu-id="e291d-122">ADOX objects</span></span>](adox-objects.md)
- [<span data-ttu-id="e291d-123">ADOX 集合</span><span class="sxs-lookup"><span data-stu-id="e291d-123">ADOX collections</span></span>](adox-collections.md)
- [<span data-ttu-id="e291d-124">ADOX 属性</span><span class="sxs-lookup"><span data-stu-id="e291d-124">ADOX properties</span></span>](adox-properties.md)
- [<span data-ttu-id="e291d-125">ADOX 方法</span><span class="sxs-lookup"><span data-stu-id="e291d-125">ADOX methods</span></span>](adox-methods.md)
- [<span data-ttu-id="e291d-126">ADOX 示例</span><span class="sxs-lookup"><span data-stu-id="e291d-126">ADOX examples</span></span>](adox-code-examples.md)

