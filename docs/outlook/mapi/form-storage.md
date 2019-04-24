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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328082"
---
# <a name="form-storage"></a>表单存储

**适用于**：Outlook 2013 | Outlook 2016 
  
尽管不必知道如何实际存储表单的所有详细信息, 但了解一些主要概念是很有用的。 因此, 在描述默认表单管理器支持的三种类型的窗体库之前, 本主题概述了窗体的存储方式。
  
表单定义可以实际存储在一个或多个 MAPI 邮件存储区中的文件夹内。 每个 MAPI 文件夹都可以被视为有两个区域用于存储邮件对象: 标准部件和关联部件。 文件夹的标准部分包括用户操作的邮件和文件夹。
  
关联部件包括与文件夹相关联的隐藏邮件对象, 包括表单定义、视图、规则模板、答复模板等。 此替换部件称为与文件夹关联的内容表, 关联的内容表中的一组邮件称为与文件夹相关的信息。 隐藏的邮件是文件夹的一个有机组成部分, 并在复制文件夹时与标准文件夹内容一起复制。 虽然物理存储为邮件, 但文件夹的关联内容表中的信息的行为与可查看的消息更像属性。 任何支持关联的内容表的 folder 对象都能够存储自定义表单。 [IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法可以返回标准内容或文件夹的关联内容, 具体取决于该方法的_ulflags_参数的值。 
  
表单库由存储在文件夹的关联内容表中的表单定义组成。 表单定义包括表单的属性、表单支持的操作, 甚至是存储为一个或多个邮件附件的表单服务器可执行文件。
  
此外, 表单可以存储在所使用的表单管理器所支持的任何文件或位置中。 默认表单管理器将表单服务器存储在 MAPI 文件夹中, 但自定义表单管理器可以实现自己的表单服务器存储。
  
一个窗体可以有多个绑定到其邮件类的用户界面。 例如, 窗体可以具有单独的撰写和读取用户界面。 该窗体负责为不同的用户请求调用适当的用户界面, 具体取决于调用的是哪个窗体谓词。 例如, 如果您的表单服务器具有单独的撰写和读取用户界面, 则当用户创建窗体的邮件类的新邮件时, 可以自动打开撰写用户界面, 并且可以在将阅读用户界面用户打开窗体的邮件类的现有邮件。
  
通过对**IMAPIFormInfo**对象调用[IMAPIFormInfo:: IMAPIProp](imapiforminfoimapiprop.md)方法, 可以获取在表单定义中存储的大部分信息。 **IMAPIFormInfo**接口通过调用检索信息所需的所有 MAPI 文件夹和邮件方法来简化对表单信息的访问。 可以通过调用[IMAPIFormContainer:: ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法来获取**IMAPIFormInfo**对象。 
  
在 "[本地表单库](local-form-libraries.md)"、"[文件夹表单库](folder-form-libraries.md)" 和 "[个人表单库](personal-form-libraries.md)" 主题中介绍了这三种类型的表单库。
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

