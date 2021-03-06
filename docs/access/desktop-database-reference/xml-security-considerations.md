---
title: XML 安全考虑事项
TOCTitle: XML Security Considerations
ms:assetid: ef2c7f59-f5a2-98d1-37c6-42cb35b26a40
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250214(v=office.15)
ms:contentKeyID: 48548575
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 648e7980be19f8af39cdb5e19858ba1ffd16518e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308244"
---
# <a name="xml-security-considerations"></a>XML 安全考虑事项


**适用于**：Access 2013、Office 2013

## <a name="xml-security-considerations"></a>XML 安全考虑事项

当在 Internet Explorer 中运行时，**Recordset** 对象的 ADO **Save** 和 **Open** 方法被视为不安全的操作。因此，如果使用这些方法的脚本代码在浏览器所宿主的应用程序或控件中运行，则该脚本代码的行为会受到浏览器安全配置的影响。

默认情况下，Internet Explorer 5 在 Internet 区域中为这样的操作提供安全限制。在该配置下， **Recordset** 不能访问客户端上的本地文件系统，也不能访问下载页面的服务器的域外部的任何数据源。特别是，当在浏览器主机内部运行时，只有当下载页面的服务器与浏览器主机为同一服务器时， **Recordset** 才能重新保存到文件中。同样，只有文件位于下载页面的同一台服务器上时，才能从文件加载 **Recordset** 来打开它。

有关 Internet Explorer 中安全性的详细信息，请参阅技术文章"Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题"。

