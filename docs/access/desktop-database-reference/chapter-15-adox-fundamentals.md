---
title: 第 15 章： ADOX 基础知识
TOCTitle: 'Chapter 15: ADOX fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6b410fcaa81aa847732e530bd18bc18200f04ebc
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936866"
---
# <a name="chapter-15-adox-fundamentals"></a><span data-ttu-id="afe66-102">第 15 章： ADOX 基础知识</span><span class="sxs-lookup"><span data-stu-id="afe66-102">Chapter 15: ADOX fundamentals</span></span>

<span data-ttu-id="afe66-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="afe66-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="afe66-p101">用于数据定义语言和安全性的 Microsoft ActiveX 数据对象扩展 (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及安全性的对象。由于它基于对象来实现对架构的操控，因此您可以编写代码来处理各类数据源，而无需考虑数据源本来的语法之间的差异。</span><span class="sxs-lookup"><span data-stu-id="afe66-p101">Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) is an extension to the ADO objects and programming model. ADOX includes objects for schema creation and modification, as well as security. Because it is an object-based approach to schema manipulation, you can write code that will work against various data sources regardless of differences in their native syntaxes.</span></span>

<span data-ttu-id="afe66-p102">ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。</span><span class="sxs-lookup"><span data-stu-id="afe66-p102">ADOX is a companion library to the core ADO objects. It exposes additional objects for creating, modifying, and deleting schema objects, such as tables and procedures. It also includes security objects to maintain users and groups and to grant and revoke permissions on objects.</span></span>

<span data-ttu-id="afe66-p103">若要将 ADOX 用于您的开发工具，应建立对 ADOX 类型库的引用。ADOX 库的描述为"Microsoft ADO Ext. for DDL and Security"。ADOX 库的文件名为 Msadox.dll，程序 ID (ProgID) 为"ADOX"。有关如何建立库引用的更多信息，请参阅您的开发工具文档。</span><span class="sxs-lookup"><span data-stu-id="afe66-p103">To use ADOX with your development tool, you should establish a reference to the ADOX type library. The description of the ADOX library is "Microsoft ADO Ext. for DDL and Security." The ADOX library file name is Msadox.dll, and the program ID (ProgID) is "ADOX". For more information about establishing references to libraries, see the documentation of your development tool.</span></span>

<span data-ttu-id="afe66-p104">Microsoft OLE DB Provider for Microsoft Jet Database Engine 完全支持 ADOX。ADOX 的某些功能可能不受支持，这取决于您的数据提供程序。有关 Microsoft OLE DB Provider for ODBC、Microsoft OLE DB Provider for Oracle 或 Microsoft SQL Server OLE DB Provider 支持的功能的更多信息，请参阅 MDAC 自述文件。</span><span class="sxs-lookup"><span data-stu-id="afe66-p104">The Microsoft OLE DB Provider for the Microsoft Jet Database Engine fully supports ADOX. Certain features of ADOX may not be supported, depending on your data provider. For more information about supported features with the Microsoft OLE DB Provider for ODBC, the Microsoft OLE DB Provider for Oracle, or the Microsoft SQL Server OLE DB Provider, see the MDAC readme file.</span></span>

<span data-ttu-id="afe66-117">本文档假定使用知识的 Microsoft Visual Basic 编程语言和 ADO 的常规知识。</span><span class="sxs-lookup"><span data-stu-id="afe66-117">This document assumes a working knowledge of the Microsoft Visual Basic programming language and a general knowledge of ADO.</span></span> <span data-ttu-id="afe66-118">有关 ADO 的详细信息，请参阅[ADO 程序员指南 》](ado-programmer-s-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="afe66-118">For more information about ADO, see the [ADO programmer's guide](ado-programmer-s-guide.md).</span></span>

<span data-ttu-id="afe66-119">本章包括以下主题：</span><span class="sxs-lookup"><span data-stu-id="afe66-119">This chapter covers the following topic:</span></span>

- [<span data-ttu-id="afe66-120">对 ADOX 的提供程序支持</span><span class="sxs-lookup"><span data-stu-id="afe66-120">Provider support for ADOX</span></span>](provider-support-for-adox.md)

<span data-ttu-id="afe66-121">有关 ADOX 的更多概述信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="afe66-121">For more overview information about ADOX, see the following topics:</span></span>

- [<span data-ttu-id="afe66-122">ADOX 对象</span><span class="sxs-lookup"><span data-stu-id="afe66-122">ADOX objects</span></span>](adox-objects.md)
- [<span data-ttu-id="afe66-123">ADOX 集合</span><span class="sxs-lookup"><span data-stu-id="afe66-123">ADOX collections</span></span>](adox-collections.md)
- [<span data-ttu-id="afe66-124">ADOX 属性</span><span class="sxs-lookup"><span data-stu-id="afe66-124">ADOX properties</span></span>](adox-properties.md)
- [<span data-ttu-id="afe66-125">ADOX 方法</span><span class="sxs-lookup"><span data-stu-id="afe66-125">ADOX methods</span></span>](adox-methods.md)
- [<span data-ttu-id="afe66-126">ADOX 示例</span><span class="sxs-lookup"><span data-stu-id="afe66-126">ADOX examples</span></span>](adox-code-examples.md)

