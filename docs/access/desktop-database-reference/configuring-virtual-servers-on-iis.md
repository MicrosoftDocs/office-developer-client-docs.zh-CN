---
title: 在 IIS 上配置虚拟服务器
TOCTitle: Configuring virtual servers on IIS
ms:assetid: 0a8057a2-c90b-d0b5-21c8-5343e80708ce
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248837(v=office.15)
ms:contentKeyID: 48543154
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f8ab3bf8e6ffec2b72744d3abacceb4725c98b02
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946725"
---
# <a name="configuring-virtual-servers-on-iis"></a>在 IIS 上配置虚拟服务器

**适用于**： Access 2013、 Office 2013

当在 Internet 信息服务 4.0 中创建虚拟服务器时，还需要额外执行下面的两个步骤，以便将虚拟服务器配置为与 RDS 一起工作：

1.  当设置服务器时，请选择"Allow Execute Access"。

2.  将 msadcs.dll 移到*vroot*\\msadc，其中 *，vroot*是虚拟服务器的主目录。

