---
title: ADO 系列库
TOCTitle: The ADO family of libraries
ms:assetid: 9e794509-d0a8-2e5b-02a8-65e26f059c4e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249724(v=office.15)
ms:contentKeyID: 48546656
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 296e05118054ec045c23cd92a399afdc3cddd9a1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718215"
---
# <a name="the-ado-family-of-libraries"></a><span data-ttu-id="0738a-102">ADO 系列库</span><span class="sxs-lookup"><span data-stu-id="0738a-102">The ADO family of libraries</span></span>

<span data-ttu-id="0738a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0738a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0738a-104">ADO 系列包括三个主要库：ADO（包括 RDS）、ADO MD 和 ADOX。</span><span class="sxs-lookup"><span data-stu-id="0738a-104">Three major libraries make up the ADO family: ADO (including RDS), ADO MD, and ADOX.</span></span>

## <a name="ado"></a><span data-ttu-id="0738a-105">ADO</span><span class="sxs-lookup"><span data-stu-id="0738a-105">ADO</span></span>

<span data-ttu-id="0738a-106">利用 ADO，您的客户端应用程序可以通过 OLE DB 提供程序访问和操控数据库服务器中的数据。</span><span class="sxs-lookup"><span data-stu-id="0738a-106">ADO enables your client applications to access and manipulate data from a database server through an OLE DB provider.</span></span> <span data-ttu-id="0738a-107">ADO 的主要优势在于易用、高速、低内存开销而且磁盘空间需求量小。</span><span class="sxs-lookup"><span data-stu-id="0738a-107">The primary benefits of ADO are ease of use, high speed, low memory overhead, and a small disk footprint.</span></span> <span data-ttu-id="0738a-108">ADO 支持用于生成客户端/服务器和基于 web 的应用程序的主要功能。</span><span class="sxs-lookup"><span data-stu-id="0738a-108">ADO supports key features for building client/server and web-based applications.</span></span>

<span data-ttu-id="0738a-109">ADO 还提供了远程数据服务 (RDS)，可以通过其移动数据从服务器到客户端应用程序或网页，操作在客户端上的数据和往返返回到在单个服务器的更新。</span><span class="sxs-lookup"><span data-stu-id="0738a-109">ADO also features Remote Data Service (RDS), by which you can move data from a server to a client application or webpage, manipulate the data on the client, and return updates to the server in a single round trip.</span></span>

## <a name="ado-md"></a><span data-ttu-id="0738a-110">ADO MD</span><span class="sxs-lookup"><span data-stu-id="0738a-110">ADO MD</span></span>

<span data-ttu-id="0738a-p102">使用 Microsoft ActiveX 数据对象（多维） (ADO MD) 可以通过 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 等语言轻松访问多维数据。ADO MD 对 ADO 进行了扩展以包含特定于多维数据的对象（如 **CubeDef** 和 **Cellset** ）。利用 ADO MD，您可以浏览多维架构，查询多维数据集，并可以检索结果。</span><span class="sxs-lookup"><span data-stu-id="0738a-p102">Microsoft ActiveX Data Objects (Multidimensional) (ADO MD) provides easy access to multidimensional data from languages such as Microsoft Visual Basic, Microsoft Visual C++, and Microsoft Visual J++. ADO MD extends ADO to include objects specific to multidimensional data, such as the **CubeDef** and **Cellset** objects. With ADO MD you can browse multidimensional schema, query a cube, and retrieve the results.</span></span>

<span data-ttu-id="0738a-p103">与 ADO 一样，ADO MD 使用基础 OLE DB 提供程序获取对数据的访问。若要使用 ADO MD，该提供程序必须是按照 OLE DB for OLAP 规范定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，这与以表格视图显示数据的表格式数据提供程序 (TDP) 不同。有关特定语法以及您的提供程序所支持的行为的更详细信息，请参考 OLAP OLE DB 提供程序的文档。</span><span class="sxs-lookup"><span data-stu-id="0738a-p103">Like ADO, ADO MD uses an underlying OLE DB provider to gain access to data. To work with ADO MD, the provider must be a multidimensional data provider (MDP) as defined by the OLE DB for OLAP specification. MDPs present data in multidimensional views as opposed to tabular data providers (TDPs) that present data in tabular views. Refer to the documentation for your OLE DB for OLAP provider for more detailed information about the specific syntax and behaviors supported by your provider.</span></span>

## <a name="adox"></a><span data-ttu-id="0738a-118">ADOX</span><span class="sxs-lookup"><span data-stu-id="0738a-118">ADOX</span></span>

<span data-ttu-id="0738a-p104">Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及保证安全性的对象。由于它基于对象实现架构操作，因此可以针对各种数据源编写代码，无需考虑其本机语法的差异。</span><span class="sxs-lookup"><span data-stu-id="0738a-p104">Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) is an extension to the ADO objects and programming model. ADOX includes objects for schema creation and modification as well as security. Because it is an object-based approach to schema manipulation, you can write code that will work against various data sources regardless of differences in their native syntaxes.</span></span>

<span data-ttu-id="0738a-p105">ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改、删除架构对象（如表和过程）的其他对象。它还包括安全性对象，用于维护用户和组以及授予和吊销对象权限。</span><span class="sxs-lookup"><span data-stu-id="0738a-p105">ADOX is a companion library to the core ADO objects. It exposes additional objects for creating, modifying, and deleting schema objects, such as tables and procedures. It also includes security objects to maintain users and groups, and to grant and revoke permissions on objects.</span></span>

