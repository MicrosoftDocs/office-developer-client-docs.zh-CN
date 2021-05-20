---
title: HrGetGALFromEmsmdbUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9b824e70-ed9a-490c-b777-8902a793fece
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9a31fec93ec7fafc4d1565d63e4bc427ba4050e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439105"
---
# <a name="hrgetgalfromemsmdbuid"></a>HrGetGALFromEmsmdbUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回由 _pEmsmdbUID_ 标识的 Exchange 的全局通讯簿的条目标识符。 应该使用 [MAPIFreeBuffer](mapifreebuffer.md)释放返回的条目标识符。
  
|||
|:-----|:-----|
|标头文件：  <br/> |abhelp.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a>参数

 _pSess_
  
> [in]登录的 IMAPISession。 它不能为 NULL。
    
 _pAddrBook_
  
> [in]用于打开条目标识符的通讯簿。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]指向标识要检索的 Exchange 服务的 GAL 的 **emsmdbUID** 的指针。 如果 _pEmsmdbUID_ 为 NULL 或零 UID，则此函数将获取 Exchange Service 的旧 GAL。 
    
 _lpc一d_
  
> [out]指向全局地址列表条目标识符的字节计数的指针。
    
 _lppeid_
  
> [out]指向全局地址列表的条目标识符的指针。 这应该使用 [MAPIFreeBuffer 释放](mapifreebuffer.md)。
    

