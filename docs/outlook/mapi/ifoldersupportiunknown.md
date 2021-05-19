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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415773"
---
# <a name="ifoldersupport--iunknown"></a>IFolderSupport : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供有关文件夹对共享的支持的信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |邮件存储提供程序  <br/> |
|接口标识符：  <br/> |IID_IFolderSupport  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[GetSupportMask](ifoldersupport-getsupportmask.md)** <br/> |获取文件夹对共享的支持信息。  <br/> |
   
## <a name="remarks"></a>备注

通常，Microsoft Office Outlook需要 MAPI 存储提供程序来实现此接口（如果提供程序想要共享文件夹）。 例外情况是Exchange Server提供程序，无需实现此接口即可共享文件夹。
  
客户端可以查询 **[IMAPIFolder](imapifolderimapicontainer.md)** 的 **IFolderSupport**。 如果成功，请调用 **IFolderSupport：：GetSupportMask** 并检查要 **FS_SUPPORTS_SHARING位。** 
  

