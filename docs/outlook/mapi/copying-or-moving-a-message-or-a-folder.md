---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: c5e92c44d7078560ed84d72b3477d5cf2e809353
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413498"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a>复制或移动邮件或文件夹
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以使用以下四种方法之一来复制或移动邮件或文件夹:
  
- [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
- [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
- [IMAPIProp::CopyTo](imapiprop-copyto.md)
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)
    
通过设置适当的标志和参数, 可以对**CopyTo**和**CopyProps**进行操作, 就像**CopyFolder**或**CopyMessages**一样。 在决定要调用哪种方法时, 请考虑以下问题:
  
- 您是否正在复制或移动文件夹或邮件？
    
- 您知道要移动或复制的文件夹或邮件需要多少钱？
    
- 将移动或复制多少个文件夹或邮件的属性？
    
您可以使用**IMAPIProp**方法复制或移动文件夹或邮件。 **IMAPIFolder:: CopyMessages**仅处理邮件;**IMAPIFolder:: CopyFolder**仅处理文件夹。 
  
而使用**IMAPIFolder**方法不需要了解要复制或移动的文件夹或邮件所支持的属性, 但必须有一些知识才能使用**IMAPIProp**方法。 使用**IMAPIProp:: CopyProps**, 您必须能够明确指定要复制或移动的文件夹或邮件属性。 使用**IMAPIProp:: CopyTo**, 除非要复制或移动所有属性, 否则必须明确指定应排除的属性。 有关这些方法的详细信息, 请参阅[复制 MAPI 属性](copying-mapi-properties.md)。
  
要复制或移动的属性的数量可能会影响要使用的方法的决定。 如果要复制或移动多封邮件, 请调用**IMAPIFolder:: CopyMessages**。 另一种选择是调用**IMAPIProp:: CopyProps**以仅复制文件夹的**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。 下面的过程演示如何使用**CopyMessages**。 
  
### <a name="to-copy-or-move-one-or-more-messages"></a>复制或移动一个或多个邮件
  
1. 查找源和目标文件夹的有效条目标识符。
    
2. 通过调用[IMAPISession:: OpenEntry](imapisession-openentry.md)或[IMsgStore:: OpenEntry](imsgstore-openentry.md)并设置 MAPI_MODIFY 标志, 可以在读/写模式下打开这些文件夹。 
    
3. 检查从**OpenEntry**返回的接口指针是否为**IMAPIFolder**接口指针。 如果不是, 则将其强制转换为 LPMAPIFOLDER 类型。 
    
4. 创建条目标识符的数组, 表示要复制或移动的一个或多个邮件。 
    
5. 使用以下标志集调用**IMAPIFolder:: CopyMessages** : 
    
   - MESSAGE_MOVE, 如果要执行移动操作。 
    
   - MESSAGE_DIALOG 并在_ulUIParam_参数中传递窗口句柄 (如果希望文件夹显示进度指示器)。 
    
6. 释放源和目标文件夹的**IMAPIFolder**指针。 
    
如果要将文件夹的完整内容复制到另一个文件夹, 请调用源文件夹的**IMAPIFolder:: CopyFolder**或**IMAPIProp:: CopyTo**方法。 
  
若要复制文件夹的一些属性, 请调用其**IMAPIProp:: CopyProps**方法。 若要复制文件夹的大部分属性, 请调用**IMAPIProp:: CopyTo**。 
  
例如, 如果要复制文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性, 您可以选择以下选项:
  
- 调用**IMAPIFolder:: CopyFolder**以复制所有文件夹属性, 然后从新文件夹中删除不需要的属性。 
    
- 调用**CopyTo**并排除除**PR_DISPLAY_NAME**和**PR_COMMENT**之外的所有文件夹属性。 
    
- 调用**CopyProps**, 在 include 数组中传递**PR_DISPLAY_NAME**和**PR_COMMENT** 。 
    
在这种情况下, **CopyProps**是最佳选择, 因为它旨在用于复制一小部分属性, 并且是实现最简单的调用。 
  
若要仅复制或移动文件夹属性, 而不包括邮件, 请调用文件夹的**IMAPIProp:: CopyTo**方法, 并排除以下属性: 
  
- **PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))
    
- **PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))
    
copy 方法可返回 S_OK, 指示 total success, MAPI_W_PARTIAL_COMPLETION, 指示部分成功或错误。 如果返回 MAPI_W_PARTIAL_COMPLETION, 则使用**HR_FAILED**宏访问更具体的错误。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
  
如果将邮件从一个邮件存储复制到另一个邮件存储, 且不支持 Unicode, 请注意, 由于代码页转换, 信息可能会丢失。 通常情况下, 您无法知道邮件存储区是否支持一种或两种格式, 这样做无法确定是将文本属性复制为 ASCII 字符串, 也不能将其复制为 Unicode 字符串。 如果你支持 unicode, 请尝试执行 unicode 复制;如果失败, 并出现错误值 MAPI_E_BAD_CHARWIDTH, 请使用 ASCII。
  

