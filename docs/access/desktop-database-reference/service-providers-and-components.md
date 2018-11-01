---
title: 服务提供程序和组件
TOCTitle: Service Providers and Components
ms:assetid: e42d9c84-525a-4aca-01b2-88e3f2b0717f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250163(v=office.15)
ms:contentKeyID: 48548333
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d215c7c66c489e54d513941604b1c66c0e9094c1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881207"
---
# <a name="service-providers-and-components"></a>服务提供程序和组件


**适用于**： Access 2013、 Office 2013

服务提供程序是一些组件，它们可以通过实现数据存储区在本地不支持的扩展接口来扩展数据提供程序的功能。

Microsoft 数据访问提供允许单个专门的组件来实现离散*组件体系结构*功能较少的存储区上设置的数据库功能或"服务"。 因此，服务组件提供了一个可供任何应用程序在访问任意数据存储区时使用的公共实现，而不是强制每个数据存储区提供扩展功能的各自实现，也不强制通用应用程序在内部实现数据库功能。 某些功能可以由数据存储区在本地实现，某些功能可以通过普通组件来实现，这一情况对于应用程序是透明的。

例如，游标引擎（如 Microsoft Cursor Service for OLE DB）就是一种服务组件，可以使用仅向前型的顺序存储区中的数据生成可滚动数据。ADO 常用的其他服务提供程序包括 Microsoft OLE DB Persistence Provider（用于将数据保存到文件）、Microsoft Data Shaping Service for OLE DB（用于分层 **Recordset**）和 Microsoft OLE DB Remoting Provider（用于调用远程计算机上的数据提供程序）。

有关服务提供程序和数据提供程序的详细信息，请参阅[附录 A：提供程序](appendix-a-providers.md)。

