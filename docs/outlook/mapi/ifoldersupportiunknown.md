---
title: IFolderSupport IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IFolderSupport
api_type:
- COM
ms.assetid: a4b03a66-cf6d-cd20-f1df-b247d3ee87aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da186e6804fc3d3c820551fee66519a2ff76f0db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351385"
---
# <a name="ifoldersupport--iunknown"></a>IFolderSupport : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供有关文件夹支持共享的信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |邮件存储区提供程序  <br/> |
|接口标识符:  <br/> |IID_IFolderSupport  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[GetSupportMask](ifoldersupport-getsupportmask.md)** <br/> |获取有关文件夹支持共享的信息。  <br/> |
   
## <a name="remarks"></a>注解

通常, 如果提供程序想要共享文件夹, Microsoft Office Outlook 需要 MAPI 存储提供程序来实现此接口。 例外情况是 Exchange 服务器存储提供程序, 它可以在不实现此接口的情况下共享文件夹。
  
客户端可以查询**IFolderSupport**的**[IMAPIFolder](imapifolderimapicontainer.md)** 。 如果成功, 请调用**IFolderSupport:: GetSupportMask**并检查要设置的**FS_SUPPORTS_SHARING**位。 
  

