---
title: 自定义 Microsoft Access 数据库引擎的 Windows 注册表设置
TOCTitle: Customizing Windows registry settings for the Microsoft Access database engine
ms:assetid: ca7e958a-ea26-d67d-45b9-10aeb1eac96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834346(v=office.15)
ms:contentKeyID: 48547690
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032168
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7cbe8ad56e01249563f7b06c9018d923a96246e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295119"
---
# <a name="customizing-windows-registry-settings-for-the-microsoft-access-database-engine"></a>自定义 Microsoft Access 数据库引擎的 Windows 注册表设置

**适用于**：Access 2013、Office 2013

如果您的应用程序无法使用 microsoft Access 数据库引擎的默认功能正常运行, 则您可能需要更改 microsoft Windows 注册表中的设置以满足您的需求。 Windows 注册表也可用于调整可安装的 ISAM 和 ODBC 驱动程序的操作。

自定义 Windows 注册表设置有以下四种不同的方式：

- [使用 regedit.exe 覆盖默认设置](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-regedit-exe-to-overwrite-the-default-settings)
- [在应用程序的注册表树中创建一个部分来管理设置](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/creating-a-portion-in-your-application-s-registry-tree-to-manage-the-settings)
- [使用 DAO 的 SetOption 方法](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-the-setoption-method-from-dao)
- [使用 Microsoft OLE DB Provider for Access 中的连接属性](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-the-connection-properties-in-the-microsoft-ole-db-provider-for-access)

