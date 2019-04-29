---
title: 邮件存储提供程序的必需和可选接口
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc62e57e-82a4-4f37-8d1b-7cdf828b951e
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 35b1d05d742b0d8defabf84b6dbf7d418ece0bbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420918"
---
# <a name="required-and-optional-interfaces-for-message-store-providers"></a>邮件存储提供程序的必需和可选接口

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义了一组与邮件存储提供程序相关的接口。 由于邮件存储区可以选择实现的功能范围很广, 因此某些接口是必需的, 而有些则不是。 下表列出了与邮件存储提供程序相关的 MAPI 接口, 指定这些接口是必需的还是可选的, 并说明其用途。
  
|**接口**|**状态**|**说明**|
|:-----|:-----|:-----|
|[IMSProvider](imsprovideriunknown.md) <br/> |必需  <br/> |登录和注销邮件存储。  <br/> |
|[IMSLogon](imslogoniunknown.md) <br/> |必需  <br/> |打开文件夹或邮件, 验证邮件存储区的标识并处理通知。  <br/> |
|[IMsgStore](imsgstoreimapiprop.md) <br/> |必需  <br/> |打开文件夹或邮件, 查找特殊文件夹并处理邮件提交。  <br/> |
|[IMAPIFolder](imapifolderimapicontainer.md) <br/> |必需  <br/> |查找并操纵邮件和子文件夹。  <br/> |
|[IMessage](imessageimapiprop.md) <br/> |必需  <br/> |操纵附件并设置邮件的一些属性。  <br/> |
|[IMAPITable](imapitableiunknown.md) <br/> |必需  <br/> |允许其他对象向各种 MAPI 组件提供数据集合。  <br/> |
|[IMAPIStatus](imapistatusimapiprop.md) <br/> |必需  <br/> |使客户端能够验证邮件存储的状态并执行某些配置任务。  <br/> |
|[IAttach](iattachimapiprop.md) <br/> |可选  <br/> |如果存储提供程序支持文件附件, 则访问邮件附件属性。  <br/> |
|**IStorage** <br/> |可选  <br/> |如果存储提供程序支持 OLE 对象附件, 则管理结构化存储对象。  <br/> |
|**IStream** <br/> |可选  <br/> |允许邮件和附件对象读取数据并将数据写入 stream 对象。  <br/> |
|**IStreamDocfile** <br/> |可选  <br/> |使某些服务提供程序能够打开存储对象, 如 OLE 2.0 文件格式的复合文件。  <br/> |
   
在这些接口的参考主题中记录了实现**IMAPIFolder**、 **IMessage**、 **IMAPIStatus**和**IMAPITable**所需的基本信息。 本节包含与邮件存储提供程序更直接相关的补充信息。 应按照本节中的信息和相应的参考主题来实施 MAPI 接口的其余部分。 有关实现**IStorage**、 **IStream**和**IStreamDocFile**的详细信息, 请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

