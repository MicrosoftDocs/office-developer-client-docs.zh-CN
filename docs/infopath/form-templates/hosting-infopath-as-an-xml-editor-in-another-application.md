---
title: 将 InfoPath 作为 XML 编辑器放置到另一个应用程序中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ae24b317-f486-763a-7009-e32c5cb85b59
description: Microsoft InfoPath 表单编辑环境可以承载在自定义 Windows 应用程序，它使开发人员可以将 InfoPath 表单编辑环境的业务线应用程序相集成。
ms.openlocfilehash: dd87cba7219b5647bd2b20dd67c6eb0f1811cc59
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773972"
---
# <a name="hosting-infopath-as-an-xml-editor-in-another-application"></a>将 InfoPath 作为 XML 编辑器放置到另一个应用程序中

Microsoft InfoPath 表单编辑环境可以承载在自定义 Windows 应用程序中。该功能使开发人员可以将 InfoPath 表单编辑环境集成到业务线应用程序中。编写基于 COM 的传统应用程序的开发人员可以通过引用 IPEDITOR.DLL 来使用可用的 **InfoPathEditorObject** 对象，而编写基于 Microsoft .NET 的应用程序的开发人员可以使用 **Microsoft.Office.InfoPath.FormControl** 程序集，该程序集提供基于 COM 接口的托管类型。IPEDITOR.DLL 和 **Microsoft.Office.InfoPath.FormControl** 程序集都随 InfoPath 一起安装在 C:\Program Files\Microsoft Office\Office15 或 C:\Program Files (x86)\Microsoft Office\Office15 文件夹中。 
  
MSDN 文章，承载 InfoPath 2007 表单编辑环境中自定义 Windows 表单应用程序，重点介绍**FormControl**对象以及如何将其合并到您的自定义。NET 基于应用程序。 与这篇文章关联的下载内容包含一个可提供 .NET 功能的自定义应用程序，可通过使用 COM **IOleCommandTargets** 来复制 InfoPath 表单编辑环境。
  

