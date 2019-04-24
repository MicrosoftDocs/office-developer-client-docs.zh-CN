---
title: 文件夹
TOCTitle: Folders
ms:assetid: b72b5705-d77a-4cad-873d-457b9fb6553e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184634(v=office.15)
ms:contentKeyID: 55119856
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ecf342c54d1aa2020fbfad4175a220b2aefecbe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327180"
---
# <a name="folders"></a>文件夹

本节提供涉及文件夹的示例任务。[Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象表示存储 Microsoft Outlook 项目的文件夹层次结构。文件夹的示例包括"日历"、"邮件"和"已删除邮件"文件夹。在 Outlook 主互操作程序集 (PIA) 中， **Folder** 对象的成员作为 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的成员公开。

## <a name="in-this-section"></a>本节内容

|主题|说明|
|:----|:----------|
|[将文件夹添加到文件夹列表](how-to-add-a-folder-to-the-folder-list.md) |介绍了如何使用 [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) 方法将文件夹添加到 Outlook 文件夹列表。|
|[枚举文件夹](how-to-enumerate-folders.md)  |介绍了如何通过循环访问文件夹集合来枚举文件夹。|
|[获取默认文件夹并枚举它的子文件夹](how-to-get-a-default-folder-and-enumerate-its-subfolders.md) |介绍了如何获取用户默认存储中的默认文件夹，并枚举它的子文件夹。|
|[根据文件夹路径获取文件夹](how-to-get-a-folder-based-on-its-folder-path.md)  |介绍了如何先获取文件夹路径，再获取关联的文件夹。|
|[选择文件夹并显示文件夹信息](how-to-select-a-folder-and-display-folder-information.md)  |介绍了如何以编程方式显示用户从指定文件夹列表中选择的文件夹的相关信息。|
|[获取文件夹的默认邮件类别](how-to-get-the-default-message-class-of-a-folder.md)  |介绍了如何使用 [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) 属性获取文件夹的默认邮件类别。|
|[访问在文件夹中存储为隐藏邮件的解决方案专用数据](how-to-access-solution-specific-data-stored-as-a-hidden-message-in-a-folder.md)  |介绍了如何使用 [StorageItem](https://msdn.microsoft.com/library/bb623436\(v=office.15\)) 对象来检索在文件夹中存储为特定邮件类别隐藏邮件的数据。|
|[确保文件夹级查询支持自定义项属性](how-to-ensure-that-custom-item-properties-are-supported-in-folder-level-queries.md) |演示如何确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。|

## <a name="see-also"></a>另请参阅

- [日历](calendar.md)
- [联系人](contacts.md)
- [邮件](mail.md)
- [我如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)

