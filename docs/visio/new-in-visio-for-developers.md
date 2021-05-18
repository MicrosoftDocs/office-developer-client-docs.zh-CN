---
title: Visio 中面向开发人员的新增功能
manager: soliver
ms.date: 09/18/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 7e3fb858-0ab8-bd2e-217c-c85b10d79785
description: 本文档提供了 2013 年 3 月中针对开发人员的增强功能Visio的顶级视图。 对于准备快速开始在 Visio 平台的开发人员，它为您提供了开始针对 Visio 2013 进行编码的足够详细信息。
ms.openlocfilehash: df4bc1fa493ee3976c99802400ee52691d05d20a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319815"
---
# <a name="new-in-visio-for-developers"></a>Visio 中面向开发人员的新增功能

本文档提供了 2013 年 3 月中针对开发人员的增强功能Visio的顶级视图。 对于准备快速开始在 Visio 平台的开发人员，它为您提供了开始针对 Visio 2013 进行编码的足够详细信息。
  
## <a name="introduction"></a>简介
<a name="vis15_WhatsNew_Intro"> </a>

Visio 2013 为自定义绘图解决方案提供了一个强大的平台。 新的 Automation 对象、集合、属性、方法、枚举和事件以及新的 ShapeSheet 单元格和函数为定义解决方案中元素的行为提供了更多选项。
  
Visio 2013 中开发人员感兴趣的新增功能包括新文件格式;对主题进行可靠更新;更改形状功能 (允许您将形状替换为另一个) ;新建形状效果;注释改进;在 SharePoint Server 2013 上共同授权;可自定义的图像剪辑;相对几何图形;支持Business Connectivity Services (BCS) 数据;Visio 2013 中的 Microsoft SharePoint Server Services 更新;和重复页面功能。 本主题简要概述了每个功能，并提及了与 Visual Basic for Applications (VBA) 中公开的功能相关的部分新 Visio 对象和成员。 有关这些功能以及随附的代码示例的信息，请参阅开发人员Visio[中心](https://msdn.microsoft.com/office/aa905478.aspx)。
  
> [!NOTE]
> Visio 2013 包括许多新的 ShapeSheet 单元格、行和函数，以支持 Visio。 有关 ShapeSheet for Visio 2013 中的新增功能的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。 
  
## <a name="new-file-format"></a>新文件格式
<a name="vis15_WhatsNew_NewFF"> </a>

Visio 2013 引入了一种新文件格式，该格式基于开放数据包约定 (OPC) 标准（ISO 29500，第二部分）和早期 Visio XML 文件格式 (.vdx) 中的 XML 元素。 它是压缩的，类似于用于其他 应用程序的文件格式的基于 XML 的文件格式。
  
由于 Visio 2013 和 Visio Services 在 Microsoft SharePoint Server 2013 中都支持新文件格式，因此您可以将 Visio 绘图直接保存到 SharePoint 服务器库，而无需将该文件发布为 Visio Web 绘图 (.vdw) 。 即使如此，Visio Services 仍可以读取和显示 Visio Web 绘图文件。
  
该新文件格式包括以下文件类型（按扩展名）：
  
- .vsdx（Visio 绘图）
    
- .vsdm（Visio 启用宏的绘图）
    
- .vssx（Visio 模具）
    
- .vssm（Visio 启用宏的模具）
    
- .vstx（Visio 模板）
    
- .vstm（Visio 启用宏的模板）
    
通过使用对读取和写入文件格式包包的现有支持 ([System.IO.Packaging](https://msdn.microsoft.com/library/System.IO.Packaging.aspx) ) 以及分析 XML ( [System.Xml。Linq](https://msdn.microsoft.com/library/System.Xml.Linq.aspx) ) ，您可以编程方式处理新的文件格式。 
  
Visio 2013 保留读取旧文件格式 (.vsd、.vss、.vst、.vdx、.vsx、.vtx、.vdw、.vwi) 。 Visio 2013 不会保存到上一个 Visio XML 文件格式 (.vdx) 。 可能需要重构使用以前的 Visio XML 文件格式 (.vdx) 文件的解决方案或工具才能读取新文件格式及其架构。
  
Visio Services 保留了在浏览器中显示 Visio Web 绘图 (.vdw) 格式的能力。它现在还呈现了新的 Visio 绘图 (.vsdx) 和 Visio 启用宏的 (.vsdm) 格式。
  
## <a name="themes"></a>主题
<a name="vis15_WhatsNew_Themes"> </a>

主题在 Visio 2013 中已经过重新设计，以便利用更多效果和样式，包括 Shape Art 效果的集成。 通过应用主题、使用主题变体对图表进行个性化设置以及通过“快速样式”突出显示单个形状，用户现在可以选择总体样式。 ShapeSheet 开发人员可将这些功能用于 ShapeSheet 中的新函数和单元格。
  
您还可以在 [Page](https://msdn.microsoft.com/library/7a7f37ab-b448-eb70-b4f1-c185dfbd511e%28Office.15%29.aspx)、[Shape](https://msdn.microsoft.com/library/da7a8872-4ebb-a607-e0ed-eebf68ff5630%28Office.15%29.aspx) 和 [Selection](https://msdn.microsoft.com/library/e5734140-6dbe-7de8-9695-1a22fb4ac628%28Office.15%29.aspx) 对象级别操纵主题。与主题一起使用的新 API 包括 [Page.SetTheme](https://msdn.microsoft.com/library/5a186f58-9a7a-bd8a-826b-85da75a4d59f%28Office.15%29.aspx) 方法、[Page.SetThemeVariant](https://msdn.microsoft.com/library/8393a95f-83ca-0efa-d987-ae498bfe5e9d%28Office.15%29.aspx) 方法、[Shape.SetQuickStyle](https://msdn.microsoft.com/library/aebe80cb-fae9-0be7-e903-882f6eb58b63%28Office.15%29.aspx) 方法和 [Selection.SetQuickStyle](https://msdn.microsoft.com/library/39b810b5-0738-daed-0103-8a2df07559c6%28Office.15%29.aspx) 方法。 
  
有关 Visio 2013 中新 API 的详细列表，请参阅Visio[对象](#vis15_WhatsNew_NewOM)模型更改一节。 有关 Visio 2013 中新 ShapeSheet 单元格的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。
  
## <a name="change-shape"></a>更改形状
<a name="vis15_WhatsNew_ChangeShapes"> </a>

Visio 2013 包含一个形状替换 API，它使您能够将一个或多个形状交换为模具中包含的另一个形状，同时保留原始形状中的一些本地值，如形状文本形状、形状数据或形状格式。 形状开发人员可以更新其自定义形状的 ShapeSheet 设置以指定这些形状的“更改形状”行为。 新 API 包括 [Shape.ReplaceShapes](https://msdn.microsoft.com/library/b330a63d-4e3f-0c4d-c38c-6ee806670225%28Office.15%29.aspx) 和 [Selection.ReplaceShapes](https://msdn.microsoft.com/library/dc278901-77ce-e1fe-c44f-f464bbb1c360%28Office.15%29.aspx) 方法以及 [ReplaceShape](https://msdn.microsoft.com/library/26c4e7cb-6618-6d2f-a4be-515584f8cd10%28Office.15%29.aspx) 事件。 
  
有关 Visio 2013 中新 API 的详细列表，请参阅Visio[对象](#vis15_WhatsNew_NewOM)模型更改一节。 有关 Visio 2013 中新 ShapeSheet 单元格的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。
  
## <a name="shape-effects"></a>形状效果
<a name="vis15_WhatsNew_ShapeEffects"> </a>

Visio 2013 中添加了新的形状效果，例如棱台、3-D 旋转、发光、反射和草图。 ShapeSheet 包括用于处理这些效果的新单元格。
  
有关 Visio 2013 中新 ShapeSheet 单元格的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。
  
## <a name="commenting"></a>注释
<a name="vis15_WhatsNew_Commenting"> </a>

Visio 2013 包含一种新的评论框架。 现在可以将评论与特定形状或页面进行关联。 Visio 2013 包含两个新对象[：Comments](https://msdn.microsoft.com/library/f028cc03-0ef1-8017-a936-d30d45211864%28Office.15%29.aspx)和[Comment。](https://msdn.microsoft.com/library/7cd0ee53-6b8d-a03b-ecd6-f6f6dda0f2d4%28Office.15%29.aspx) 用于以编程方式访问评论的新 API 包括 [Document.Comments](https://msdn.microsoft.com/library/15a322ad-70eb-1487-701d-76e2fde73309%28Office.15%29.aspx)、[Page.Comments](https://msdn.microsoft.com/library/9618c86c-96c0-be95-ee20-5d1b99f4d5e8%28Office.15%29.aspx)、[Shape.Comments](https://msdn.microsoft.com/library/498eca91-beb9-b764-0262-a935e5205710%28Office.15%29.aspx) 和 [Page.ShapeComments](https://msdn.microsoft.com/library/b7d86594-ba1f-627b-222f-905da1b1201e%28Office.15%29.aspx) 属性。 
  
Visio服务包括 JavaScript API，用于从图表中的页面或形状读取注释。
  
有关 Visio 2013 中新 API 的详细列表，请参阅Visio[对象](#vis15_WhatsNew_NewOM)模型更改一节。 
  
> [!NOTE]
> 注释将无法再通过 ShapeSheet 访问。 
  
## <a name="coauthoring"></a>共同创作
<a name="vis15_WhatsNew_Coauthoring"> </a>

Visio 2013 包括共同创作存储在 SharePoint 或 Microsoft OneDrive。 开发人员可以访问提供由于共同创作产生的图表更改相关信息的 [Document.AfterDocumentMerge](https://msdn.microsoft.com/library/50658da5-592a-4d16-908f-c6abe3050f09%28Office.15%29.aspx) 事件。 解决方案开发人员还必须使用 Document ShapeSheet 上的 [NoCoauth](nocoauth-cell-document-properties-section.md) 单元格，禁用共同创作以满足其特定需求的功能。 
  
有关 Visio 2013 中新 API 的详细列表，请参阅Visio[对象](#vis15_WhatsNew_NewOM)模型更改一节。 
  
## <a name="customizable-image-clipping"></a>可自定义的图像剪辑
<a name="vis15_WhatsNew_ClipImages"> </a>

Visio 2013 支持定义自定义图像剪辑路径以将图像裁剪为任意形状。 这扩展了 Visio 2010 的容量，支持以矩形方式剪裁图像。 此功能在 ShapeSheet 中可用，方法是使用“外部图像信息”部分中的[ClippingPath](clippingpath-cell-foreign-image-info-section.md) 单元格。 
  
有关 Visio 2013 中新 ShapeSheet 单元格的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。
  
## <a name="relative-geometries"></a>相对几何体
<a name="vis15_WhatsNew_RelativeGeometry"> </a>

在早期版本的 Visio 中，形状几何图形由依赖于形状的高度或宽度的公式定义。 例如，在 Visio 2010 中，许多内置 Visio 形状的顶点都是通过将形状的高度或宽度乘以一个常量定义的。 这些形状具有 **包含** [MoveTo](moveto-row-geometry-section.md) 或 [LineTo](lineto-row-geometry-section.md) 行的"Geometry"内容 (例如，) 和 等  `Width*1` 公式  `Height*0` 组合在一起。
  
Visio 2013 现在支持在 ShapeSheet 中使用相对几何体。 形状开发人员现在可以使用相对几何体将几何体指定为简单值或公式，它们会自动乘以高度或宽度。 形状顶点现在可以使用常量表示，例如，不再需要将顶点表示为形状宽度或高度的倍数。 这使得开发人员能够更轻松地创建形状，并提供更好的性能和更小的文件。 新行包括 [RelMoveTo](relmoveto-row-geometry-section.md) 和 [RelLineTo](rellineto-row-geometry-section.md) 行，其中 **X** 和 **Y** 单元格值会自动分别乘以形状的宽度或高度。 
  
有关 2013 年 Visio 中新 ShapeSheet 行的详细信息，请参阅文章[What's new for Visio ShapeSheet developers](what-s-new-for-visio-shapesheet-developers.md)。
  
## <a name="support-for-business-connectivity-services-bcs-data"></a>支持 Microsoft Business Connectivity Services (BCS) 数据
<a name="vis15_WhatsNew_BCS"> </a>

Visio 2013 图表现在可以连接到 SharePoint Server 2013 服务器中的外部列表。 外部列表是外部内容源SharePoint (例如，已使用 SQL Server) 连接到 SharePoint 列表的 Microsoft Business Connectivity Services (BCS) 。 Visio Services 支持在数据更新时刷新 Visio 图表。
  
有关 Visio Services 中的新增功能详细信息，请参阅 Visio [Services in SharePoint 2013](https://msdn.microsoft.com/library/jj164027%28office.15%29.aspx)一文。 有关此Business Connectivity Services (BCS) ，请参阅[Business Connectivity Services 2013 SharePoint。](https://msdn.microsoft.com/library/jj163782%28office.15%29.aspx)
  
## <a name="improvements-in-visio-services"></a>Visio Services 中的改进
<a name="vis15_WhatsNew_VisioServices"> </a>

VisioMicrosoft SharePoint Server 2013 中的服务包括许多改进。 如前所述，Visio Services 支持新的 Visio 文件格式， (.vsdx 和 .vsdm) 。 Visio服务已扩展数据刷新和重新计算，包括在整个图表中重新计算公式的能力。 
  
有关 Visio Services 中的新增功能详细信息，请参阅 Visio [Services in SharePoint 2013](https://msdn.microsoft.com/library/jj164027%28office.15%29.aspx)一文。
  
## <a name="duplicate-page"></a>复制页面
<a name="vis15_WhatsNew_DuplicatePage"> </a>

现在，您可以在 2013 中复制同一文档中的页面及其Visio形状。 相应地，**Page** 对象具有新方法 [Duplicate](https://msdn.microsoft.com/library/394be23b-997d-0da1-b3bd-8278564fb4e0%28Office.15%29.aspx)，它将复制页面并返回新的 **Page** 对象。 
  
## <a name="visio-object-model-changes"></a>Visio对象模型更改
<a name="vis15_WhatsNew_NewOM"> </a>

新对象、属性、方法和事件已添加到 Visio 对象模型中，以提供对新的 Visio 2013 功能的可编程性支持。 此外，对象模型改进解决了开发人员频繁请求更改 Visio 请求。
  
### <a name="new-members"></a>新成员

以下成员已添加到现有对象模型中Visio对象。
  
 **表 2. Visio 对象模型增强功能**
  
|**对象或集合**|**新成员**|
|:-----|:-----|
|[Application 对象 (Visio) ](https://msdn.microsoft.com/library/5b3c8939-793f-116f-11b8-1d4170d95a63%28Office.15%29.aspx) <br/> |[Application.AfterReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/b02de031-086a-41cc-d832-5434b8096444%28Office.15%29.aspx) <br/> |
||[Application.BeforeReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/fbf44569-0539-9292-ce20-1f9e34238b33%28Office.15%29.aspx) <br/> |
||[Application.QueryCancelReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/50c0f2a6-f534-f3af-7e83-c865abda8bf9%28Office.15%29.aspx) <br/> |
||[Application.ReplaceShapesCanceled 事件 (Visio) ](https://msdn.microsoft.com/library/e8eecd64-e4bd-d2c4-b942-c5ff607a4121%28Office.15%29.aspx) <br/> |
|[ApplicationSettings 对象 (Visio) ](https://msdn.microsoft.com/library/f2e24211-ecc6-e0f5-4c00-fc50f98a3505%28Office.15%29.aspx) <br/> |[ApplicationSettings.EnterCommitsText (Visio) ](https://msdn.microsoft.com/library/ba9ce9fa-d224-cdc3-668d-46c1849911c7%28Office.15%29.aspx) <br/> |
||[ApplicationSettings.SVGExportFormat 属性 (Visio) ](https://msdn.microsoft.com/library/9e7ca1cb-5ace-b75b-0e59-61566b9a0169%28Office.15%29.aspx) <br/> |
|[Document 对象 (Visio) ](https://msdn.microsoft.com/library/21640062-13a2-a2b2-7c61-7e707671207c%28Office.15%29.aspx) <br/> |[Document.AfterDocumentMerge 事件 (Visio) ](https://msdn.microsoft.com/library/50658da5-592a-4d16-908f-c6abe3050f09%28Office.15%29.aspx) <br/> |
||[Document.Comments 属性 (Visio) ](https://msdn.microsoft.com/library/15a322ad-70eb-1487-701d-76e2fde73309%28Office.15%29.aspx) <br/> |
||[Document.CompatibilityMode 属性 (Visio) ](https://msdn.microsoft.com/library/98fc00d3-5d2b-218e-9828-b5581ee7313d%28Office.15%29.aspx) <br/> |
|[Documents 对象 (Visio) ](https://msdn.microsoft.com/library/e9291149-964e-c6fb-4c62-bf2f35a6a0a7%28Office.15%29.aspx) <br/> |[Documents.AfterDocumentMerge 事件 (Visio) ](https://msdn.microsoft.com/library/cac0544d-77b9-b722-cfdb-e42475ce2558%28Office.15%29.aspx) <br/> |
||[Documents.AfterReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/e01c069e-440b-7b8b-8d7d-cdb664f6e2d6%28Office.15%29.aspx) <br/> |
||[Documents.BeforeReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/55a66c47-a2ca-5c8a-2693-aaa1b079c704%28Office.15%29.aspx) <br/> |
||[Documents.QueryCancelReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/d613730e-04c8-d17f-0ad1-19e976aa107d%28Office.15%29.aspx) <br/> |
||[Documents.ReplaceShapesCanceled 事件 (Visio) ](https://msdn.microsoft.com/library/94a20fe7-da09-4e3c-d048-05ba0b8f1070%28Office.15%29.aspx) <br/> |
|[InvisibleApp 对象 (Visio) ](https://msdn.microsoft.com/library/70a30571-2017-af8b-eaa1-bf93c758a46a%28Office.15%29.aspx) <br/> |[InvisibleApp.AfterReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/5d7b8ec2-ef65-1a49-fb50-3fae95d56761%28Office.15%29.aspx) <br/> |
||[InvisibleApp.BeforeReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/bd0e37ca-887a-4d53-3b0c-3339492df3dd%28Office.15%29.aspx) <br/> |
||[InvisibleApp.QueryCancelReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/5e5d9b76-dfd4-1d02-d205-9e64350449d5%28Office.15%29.aspx) <br/> |
||[InvisibleApp.ReplaceShapesCanceled 事件 (Visio) ](https://msdn.microsoft.com/library/17e43497-c7a8-8546-595c-4630afb301a3%28Office.15%29.aspx) <br/> |
|[Page 对象 (Visio) ](https://msdn.microsoft.com/library/7a7f37ab-b448-eb70-b4f1-c185dfbd511e%28Office.15%29.aspx) <br/> |[Page.AfterReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/e4005987-acb1-78d7-91fb-c3c2d5b036e3%28Office.15%29.aspx) <br/> |
||[Page.BeforeReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/57ea9836-74dd-77c2-6541-f8f61b89c0b6%28Office.15%29.aspx) <br/> |
||[Page.Comments 属性 (Visio) ](https://msdn.microsoft.com/library/9618c86c-96c0-be95-ee20-5d1b99f4d5e8%28Office.15%29.aspx) <br/> |
||[Page.Duplicate 方法 (Visio) ](https://msdn.microsoft.com/library/394be23b-997d-0da1-b3bd-8278564fb4e0%28Office.15%29.aspx) <br/> |
||[Page.GetTheme 方法 (Visio) ](https://msdn.microsoft.com/library/31c84e69-0bc8-2d1a-84d8-7397110d74ae%28Office.15%29.aspx) <br/> |
||[Page.GetThemeVariant 方法 (Visio) ](https://msdn.microsoft.com/library/40c2be31-fdb0-68ee-a129-2788b1b17c82%28Office.15%29.aspx) <br/> |
||[Page.QueryCancelReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/17ead23f-825a-c608-3315-e2eed6784cd5%28Office.15%29.aspx) <br/> |
||[Page.ReplaceShapesCanceled 事件 (Visio) ](https://msdn.microsoft.com/library/867b1fc1-96bd-cbeb-fd61-b02a96e039ca%28Office.15%29.aspx) <br/> |
||[Page.SetTheme 方法 (Visio) ](https://msdn.microsoft.com/library/5a186f58-9a7a-bd8a-826b-85da75a4d59f%28Office.15%29.aspx) <br/> |
||[Page.SetThemeVariant 方法 (Visio) ](https://msdn.microsoft.com/library/8393a95f-83ca-0efa-d987-ae498bfe5e9d%28Office.15%29.aspx) <br/> |
||[Page.ShapeComments 属性 (Visio) ](https://msdn.microsoft.com/library/b7d86594-ba1f-627b-222f-905da1b1201e%28Office.15%29.aspx) <br/> |
|[Pages 对象 (Visio) ](https://msdn.microsoft.com/library/45eec568-b5cc-5e80-ff5c-4dfa567efb5d%28Office.15%29.aspx) <br/> |[Pages.AfterReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/05c33bdd-e697-d36e-46a8-45705e9ad2c2%28Office.15%29.aspx) <br/> |
||[Pages.BeforeReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/3f6dbc31-0583-dd67-0432-335d6df7a50c%28Office.15%29.aspx) <br/> |
||[Pages.QueryCancelReplaceShapes 事件 (Visio) ](https://msdn.microsoft.com/library/d11ff976-0016-da6b-92fb-379baa7e8f94%28Office.15%29.aspx) <br/> |
||[Pages.ReplaceShapesCanceled 事件 (Visio) ](https://msdn.microsoft.com/library/f0ce8c66-7a15-5f91-8c89-e177bc6671d2%28Office.15%29.aspx) <br/> |
|[Selection 对象 (Visio) ](https://msdn.microsoft.com/library/e5734140-6dbe-7de8-9695-1a22fb4ac628%28Office.15%29.aspx) <br/> |[Selection.ReplaceShape 方法 (Visio) ](https://msdn.microsoft.com/library/dc278901-77ce-e1fe-c44f-f464bbb1c360%28Office.15%29.aspx) <br/> |
||[Selection.SetQuickStyle 方法 (Visio) ](https://msdn.microsoft.com/library/39b810b5-0738-daed-0103-8a2df07559c6%28Office.15%29.aspx) <br/> |
|[Shape 对象 (Visio)](https://msdn.microsoft.com/library/da7a8872-4ebb-a607-e0ed-eebf68ff5630%28Office.15%29.aspx) <br/> |[Shape.ChangePicture 方法 (Visio) ](https://msdn.microsoft.com/library/9193d802-cebd-2bfd-5f8e-400fac36c1a5%28Office.15%29.aspx) <br/> |
||[Shape.Comments 属性 (Visio) ](https://msdn.microsoft.com/library/498eca91-beb9-b764-0262-a935e5205710%28Office.15%29.aspx) <br/> |
||[Shape.ReplaceShape 方法 (Visio) ](https://msdn.microsoft.com/library/b330a63d-4e3f-0c4d-c38c-6ee806670225%28Office.15%29.aspx) <br/> |
||[Shape.SetQuickStyle 方法 (Visio) ](https://msdn.microsoft.com/library/aebe80cb-fae9-0be7-e903-882f6eb58b63%28Office.15%29.aspx) <br/> |
   
### <a name="new-objects-and-enumerations"></a>新对象和枚举

以下对象已添加到Visio模型中。
  
 **表 2. Visio 对象模型新增功能**
  
|**对象**|**属性**|**方法**|
|:-----|:-----|:-----|
|[CoauthMergeEvent 对象 (Visio) ](https://msdn.microsoft.com/library/eb9425cb-0108-4909-e334-9cd51e5b9303%28Office.15%29.aspx) <br/> |[CoauthMergeEvent.BaseDocument 属性 (Visio) ](https://msdn.microsoft.com/library/7ec09a85-6f51-685b-0c87-4b9eb3266773%28Office.15%29.aspx) <br/> [CoauthMergeEvent.DownloadDocument 属性 (Visio) ](https://msdn.microsoft.com/library/19239540-cd5a-13ea-3b26-282ac3676abd%28Office.15%29.aspx) <br/> [CoauthMergeEvent.ObjectType 属性 (Visio) ](https://msdn.microsoft.com/library/01baa0c2-75b7-2713-9732-1e7a8a7b33aa%28Office.15%29.aspx) <br/> [CoauthMergeEvent.Stat 属性 (Visio) ](https://msdn.microsoft.com/library/d8a96b8e-36b5-c61f-8cea-76266f7eed39%28Office.15%29.aspx) <br/> [CoauthMergeEvent.WorkingDocument 属性 (Visio) ](https://msdn.microsoft.com/library/0f3c4358-0d63-df7f-12fe-7f378bacca86%28Office.15%29.aspx) <br/> |无  <br/> |
|[注释对象 (Visio) ](https://msdn.microsoft.com/library/f028cc03-0ef1-8017-a936-d30d45211864%28Office.15%29.aspx) <br/> |[Comment.AssociatedObject 属性 (Visio) ](https://msdn.microsoft.com/library/e28eed2e-260e-59c9-9b24-631817fe1ae1%28Office.15%29.aspx) <br/> [Comment.AuthorInitials 属性 (Visio) ](https://msdn.microsoft.com/library/abc07100-8c5c-9982-674d-40b58c096816%28Office.15%29.aspx) <br/> [Comment.AuthorName 属性 (Visio) ](https://msdn.microsoft.com/library/e1da4db8-7a16-16bf-2a5f-be1ac5372d34%28Office.15%29.aspx) <br/> [Comment.AuthorSipAddress 属性 (Visio) ](https://msdn.microsoft.com/library/f8d185a9-91b6-471a-3c0e-ffa8a06b36b3%28Office.15%29.aspx) <br/> [Comment.AuthorSMTPAddress 属性 (Visio) ](https://msdn.microsoft.com/library/22e04ccc-c524-ca08-d5e2-db68fdb3afb6%28Office.15%29.aspx) <br/> [Comment.Collapsed 属性 (Visio) ](https://msdn.microsoft.com/library/9552e379-e351-78d7-e0ed-4f524c3273a1%28Office.15%29.aspx) <br/> [Comment.CreateDate 属性 (Visio) ](https://msdn.microsoft.com/library/b643e13e-da12-a992-3a59-99b37f003fb9%28Office.15%29.aspx) <br/> [Comment.Document 属性 (Visio) ](https://msdn.microsoft.com/library/d57b1377-b895-1fe1-2f98-ef000fdd9c39%28Office.15%29.aspx) <br/> [Comment.EditDate 属性 (Visio) ](https://msdn.microsoft.com/library/4ad13f54-215e-3680-5de6-13715e309fbf%28Office.15%29.aspx) <br/> [Comment.ObjectType 属性 (Visio) ](https://msdn.microsoft.com/library/bf0d786d-e1b6-65f1-3112-5dfd4ff324e9%28Office.15%29.aspx) <br/> [Comment.Stat 属性 (Visio) ](https://msdn.microsoft.com/library/f457598c-af42-cb83-ecd2-4fd42898ea16%28Office.15%29.aspx) <br/> [Comment.Text 属性 (Visio) ](https://msdn.microsoft.com/library/3ec63034-de5f-d9f2-16a5-e06a56883867%28Office.15%29.aspx) <br/> |[Comment.Delete 方法 (Visio) ](https://msdn.microsoft.com/library/7762f264-f680-5758-7c35-dfe9067b61ca%28Office.15%29.aspx) <br/> |
|[注释对象 (Visio) ](https://msdn.microsoft.com/library/7cd0ee53-6b8d-a03b-ecd6-f6f6dda0f2d4%28Office.15%29.aspx) <br/> |[Comments.Count 属性 (Visio) ](https://msdn.microsoft.com/library/abac02d5-5047-2c9d-5c5c-e2738f99a4a6%28Office.15%29.aspx) <br/> [Comments.Document 属性 (Visio) ](https://msdn.microsoft.com/library/507d4698-e282-f8a9-1299-c67945ee5fc4%28Office.15%29.aspx) <br/> [Comments.Item 属性 (Visio) ](https://msdn.microsoft.com/library/fed2a079-de87-d5ce-1d74-0bfa5a328441%28Office.15%29.aspx) <br/> [Comments.ObjectType 属性 (Visio) ](https://msdn.microsoft.com/library/06544d73-ce00-2c89-1ecb-20541b251d57%28Office.15%29.aspx) <br/> [Comments.Stat 属性 (Visio) ](https://msdn.microsoft.com/library/1f5f29b2-236c-91b6-6d25-7bacc37ca96c%28Office.15%29.aspx) <br/> |[Comments.Add 方法 (Visio) ](https://msdn.microsoft.com/library/da02de49-8057-7e5c-6b59-0a013e56256d%28Office.15%29.aspx) <br/> [Comments.DeleteAll 方法 (Visio) ](https://msdn.microsoft.com/library/50777ed3-553c-90ae-2d30-9dde412fe6b9%28Office.15%29.aspx) <br/> |
|[ReplaceShapesEvent 对象 (Visio) ](https://msdn.microsoft.com/library/26c4e7cb-6618-6d2f-a4be-515584f8cd10%28Office.15%29.aspx) <br/> |[ReplaceShapesEvent.ObjectType 属性 (Visio) ](https://msdn.microsoft.com/library/bcc442f0-aa4e-cd5a-d116-f3fb74459927%28Office.15%29.aspx) <br/> [ReplaceShapesEvent.ReplaceFlags 属性 (Visio) ](https://msdn.microsoft.com/library/d0d00891-c794-bd0c-d37e-1ab98c92beab%28Office.15%29.aspx) <br/> [ReplaceShapesEvent.ReplacementMaster 属性 (Visio) ](https://msdn.microsoft.com/library/326a1889-8952-b4ac-c5c0-ac4470257c06%28Office.15%29.aspx) <br/> [ReplaceShapesEvent.SelectionSource 属性 (Visio) ](https://msdn.microsoft.com/library/f81c0b66-b63b-fc7c-1769-d56a17d5cf78%28Office.15%29.aspx) <br/> [ReplaceShapesEvent.Stat 属性 (Visio) ](https://msdn.microsoft.com/library/96f3d382-5dda-7f93-088d-96edc831cd7c%28Office.15%29.aspx) <br/> |无  <br/> |
   
下表列出了 2013 年 10 月引入的新枚举Visio常量。
  
 **表 3. Visio 枚举新增功能**
  
|**枚举**|**说明**|
|:-----|:-----|
|[VisQuickStyleColors 枚举 (Visio) ](https://msdn.microsoft.com/library/c19d91f3-a9a4-e31e-ed7a-eef15553fbf4%28Office.15%29.aspx) <br/> |为主题中包含的颜色指定名称。  <br/> |
|[VisQuickStyleMatrixIndices 枚举 (Visio) ](https://msdn.microsoft.com/library/0fb0b448-85ba-4fc4-d933-21d574cefa2a%28Office.15%29.aspx) <br/> |为 2013 年 10 月提供的主题和变体Visio名称。  <br/> |
|[VisReplaceFlags 枚举 (Visio) ](https://msdn.microsoft.com/library/cf270178-f939-7eb4-b8e1-3b4153aff221%28Office.15%29.aspx) <br/> |指定“更改形状”操作的行为。  <br/> |
|[VisSVGExportFormat 枚举 (Visio) ](https://msdn.microsoft.com/library/d8ca8c3f-41d9-4e9d-8f6d-f5567361b14e%28Office.15%29.aspx) <br/> |指定将图表导出到 SVG 时包括或排除 Visio 标记。  <br/> |
   
### <a name="deprecated-objects-and-members"></a>不建议使用的对象和成员

下表列出了 2013 年 10 月中引入的弃Visio和成员。 **不建议使用的成员** 列中仅列出不建议使用的对象成员。 
  
 **表 4. Visio 对象模型弃用功能**
  
|**对象或集合**|**不建议使用的成员**|
|:-----|:-----|
|**Window** 对象  <br/> |**PageTabWidth** 属性  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="vis15_WhatsNew_Additional"> </a>

- [Visio 开发人员参考](https://msdn.microsoft.com/office/aa905478.aspx)
    
- [面向 Visio ShapeSheet 开发人员的新增功能](what-s-new-for-visio-shapesheet-developers.md)
    
- [SharePoint 2013 中的 Visio Services](https://msdn.microsoft.com/library/jj164027%28office.15%29.aspx)
    
- [Visio (Office.com) ](https://office.com/redir/HA102749364.aspx)
    
- [Visio 开发中心](https://msdn.microsoft.com/office/aa905478.aspx)
    

