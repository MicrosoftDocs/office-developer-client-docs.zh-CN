---
title: 表单存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ddf9158-3c10-408a-aeaf-5a382c4339e7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 793a34b093ba69f73be7e186bec0a769584bbac4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414891"
---
# <a name="form-storage"></a>表单存储

**适用于**：Outlook 2013 | Outlook 2016 
  
尽管不需要了解表单物理存储方式的所有详细信息，但了解一些主要概念会很有用。 因此，在介绍默认表单管理器支持的三种类型的表单库之前，本主题概述了如何存储表单。
  
表单定义可以物理存储在一个或多个 MAPI 邮件存储的文件夹中。 可以将每个 MAPI 文件夹视为具有两个存储邮件对象的区域：标准部件和关联部件。 文件夹的标准部分包括用户操作的邮件和文件夹。
  
关联的部件包括与文件夹关联的隐藏邮件对象，包括表单定义、视图、规则模板、回复模板等。 此备用部件称为文件夹相关内容表，关联内容表中的邮件集称为文件夹相关信息。 隐藏邮件是文件夹的组成部分，复制文件夹时，会与标准文件夹内容一起复制。 虽然以物理方式存储为邮件，但文件夹的关联内容表中的信息的行为更像属性，而不是像可查看邮件一样。 支持关联内容表的任何文件夹对象都能够存储自定义窗体。 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)方法可以返回文件夹的标准内容或关联内容，具体取决于该方法 _的 ulflags_ 参数的值。 
  
表单库由存储在文件夹的关联内容表中的表单定义组成。 表单定义包括表单的属性、表单支持的操作，甚至是存储为一个或多个邮件附件的表单服务器可执行文件。
  
此外，表单还可以存储在所使用的表单管理器支持的任何文件或位置中。 默认表单管理器将表单服务器存储在 MAPI 文件夹中，但自定义表单管理器可以针对表单服务器实现自己的存储。
  
表单可以有多个绑定到其邮件类的用户界面。 例如，窗体可以有单独的"撰写"和"阅读"用户界面。 表单负责为不同的用户请求调用正确的用户界面，具体取决于调用了表单的哪些谓词。 例如，如果您的窗体服务器具有单独的撰写和阅读用户界面，则当用户创建窗体的邮件类的新邮件时，可以自动打开"撰写"用户界面，并且当用户打开窗体的邮件类的现有邮件时，将自动打开"阅读"用户界面。
  
通过调用 [IMAPIFormInfo：：IMAPIProp](imapiforminfoimapiprop.md) 方法，可在 **表单** 定义中存储大部分信息。 **IMAPIFormInfo** 接口通过调用检索信息所需的所有 MAPI 文件夹和消息方法来简化对表单信息的访问。 可以通过调用 [IMAPIFormContainer：：ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法获取 **IMAPIFormInfo** 对象。 
  
The three types of form libraries are described in the topics [Local Form Libraries，](local-form-libraries.md) [Folder Form Libraries](folder-form-libraries.md) and Personal Form [Libraries](personal-form-libraries.md).
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

