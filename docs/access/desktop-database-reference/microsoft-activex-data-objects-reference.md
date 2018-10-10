---
title: Microsoft ActiveX 数据对象的引用
TOCTitle: Microsoft ActiveX Data Objects Reference
ms:assetid: 235fc575-8a2e-913c-fa3d-bb86256733f9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249010(v=office.15)
ms:contentKeyID: 48543728
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5426dd17e174c0aa95517885fd43e7d00f21342b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467230"
---
# <a name="microsoft-activex-data-objects-reference"></a><span data-ttu-id="c27f2-102">Microsoft ActiveX 数据对象的引用</span><span class="sxs-lookup"><span data-stu-id="c27f2-102">Microsoft ActiveX Data Objects reference</span></span>

<span data-ttu-id="c27f2-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c27f2-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="purpose"></a><span data-ttu-id="c27f2-104">目的</span><span class="sxs-lookup"><span data-stu-id="c27f2-104">Purpose</span></span>

<span data-ttu-id="c27f2-p101">Microsoft ActiveX 数据对象 (ADO) 使您的客户端应用程序可以通过 OLE DB 提供程序访问和操控数据库服务器中的数据。它的主要优点是简单易用、高速、内存开销低和磁盘占用小。ADO 支持用于构建客户端/服务器和基于 Web 的应用程序的关键功能。</span><span class="sxs-lookup"><span data-stu-id="c27f2-p101">Microsoft ActiveX Data Objects (ADO) enable your client applications to access and manipulate data from a database server through an OLE DB provider. Its primary benefits are ease of use, high speed, low memory overhead, and a small disk footprint. ADO supports key features for building client/server and Web-based applications.</span></span>

## <a name="rds"></a><span data-ttu-id="c27f2-108">RDS</span><span class="sxs-lookup"><span data-stu-id="c27f2-108">RDS</span></span>

<span data-ttu-id="c27f2-109">ADO 还提供了远程数据服务 (RDS)，利用它可以将数据从服务器移动到客户端应用程序或网页，在客户端上操控数据，然后在单个来回行程中将更新返回给服务器。</span><span class="sxs-lookup"><span data-stu-id="c27f2-109">ADO also features Remote Data Service (RDS), by which you can move data from a server to a client application or Web page, manipulate the data on the client, and return updates to the server in a single round trip.</span></span>

## <a name="ado-md"></a><span data-ttu-id="c27f2-110">ADO MD</span><span class="sxs-lookup"><span data-stu-id="c27f2-110">ADO MD</span></span>

<span data-ttu-id="c27f2-p102">使用 Microsoft ActiveX 数据对象（多维）(ADO MD) 可以通过如 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 这样的语言轻松访问多维数据。ADO MD 扩展了 Microsoft ActiveX 数据对象 (ADO)，将特定于多维数据的对象（如 CubeDef 和 Cellset 对象）包括在其中。利用 ADO MD，您可以浏览多维架构，查询多维数据集，并检索结果。</span><span class="sxs-lookup"><span data-stu-id="c27f2-p102">Microsoft ActiveX Data Objects (Multidimensional) (ADO MD) provides easy access to multidimensional data from languages such as Microsoft Visual Basic, Microsoft Visual C++, and Microsoft Visual J++. ADO MD extends Microsoft ActiveX Data Objects (ADO) to include objects specific to multidimensional data, such as the CubeDef and Cellset objects. With ADO MD you can browse multidimensional schema, query a cube, and retrieve the results.</span></span>

<span data-ttu-id="c27f2-p103">与 ADO 相仿，ADO MD 也使用基础 OLE DB 提供程序来获得对数据的访问。为了使用 ADO MD，您的提供程序必须是 OLE DB for OLAP 规范所定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，与此相对，表格式数据提供程序 (TDP) 则以表格式视图显示数据。有关您的提供程序所支持的特定语法和行为的更多详细信息，请参考您的 OLAP OLE DB 提供程序的文档。</span><span class="sxs-lookup"><span data-stu-id="c27f2-p103">Like ADO, ADO MD uses an underlying OLE DB provider to gain access to data. To work with ADO MD, the provider must be a multidimensional data provider (MDP) as defined by the OLE DB for OLAP specification. MDPs present data in multidimensional views as opposed to tabular data providers (TDPs) that present data in tabular views. Refer to the documentation for your OLAP OLE DB provider for more detailed information on the specific syntax and behaviors supported by your provider.</span></span>

## <a name="adox"></a><span data-ttu-id="c27f2-118">ADOX</span><span class="sxs-lookup"><span data-stu-id="c27f2-118">ADOX</span></span>

<span data-ttu-id="c27f2-p104">用于数据定义语言和安全性的 Microsoft ActiveX 数据对象扩展 (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及安全性的对象。由于它基于对象来实现对架构的操控，因此您可以编写代码来处理各类数据源，而无需考虑数据源本来的语法之间的差异。</span><span class="sxs-lookup"><span data-stu-id="c27f2-p104">Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) is an extension to the ADO objects and programming model. ADOX includes objects for schema creation and modification, as well as security. Because it is an object-based approach to schema manipulation, you can write code that will work against various data sources regardless of differences in their native syntaxes.</span></span>

<span data-ttu-id="c27f2-p105">ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。</span><span class="sxs-lookup"><span data-stu-id="c27f2-p105">ADOX is a companion library to the core ADO objects. It exposes additional objects for creating, modifying, and deleting schema objects, such as tables and procedures. It also includes security objects to maintain users and groups and to grant and revoke permissions on objects.</span></span>

## <a name="ado-25-main-components"></a><span data-ttu-id="c27f2-125">ADO 2.5 主要组件</span><span class="sxs-lookup"><span data-stu-id="c27f2-125">ADO 2.5 main components</span></span>

- <span data-ttu-id="c27f2-126">[程序员指南](ado-programmer-s-guide.md)： 使用 ADO、 RDS、 ADO MD 和 ADOX 的介绍。</span><span class="sxs-lookup"><span data-stu-id="c27f2-126">[Programmer's guide](ado-programmer-s-guide.md): An introduction to using ADO, RDS, ADO MD, and ADOX.</span></span>

- <span data-ttu-id="c27f2-127">[程序员参考](ado-programmer-s-reference-topics.md)： ADO 文档中的此部分包含的每个 ADO、 RDS、 ADO MD 和 ADOX 对象的集合、 属性、 动态属性、 方法、 事件和枚举的主题。</span><span class="sxs-lookup"><span data-stu-id="c27f2-127">[Programmer's reference](ado-programmer-s-reference-topics.md): This section of the ADO documentation contains topics for each ADO, RDS, ADO MD, and ADOX object, collection, property, dynamic property, method, event, and enumeration.</span></span>

## <a name="feedback"></a><span data-ttu-id="c27f2-128">反馈</span><span class="sxs-lookup"><span data-stu-id="c27f2-128">Feedback</span></span>

<span data-ttu-id="c27f2-129">可以直接向 ADO 文档工作组发送关于 ADO 文档或示例的反馈。</span><span class="sxs-lookup"><span data-stu-id="c27f2-129">You can send feedback about ADO documentation or samples directly to the ADO documentation team.</span></span>

