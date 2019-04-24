---
title: 创建简单邮件项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bbf99c4b-3008-4475-a60a-648eaed59d01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8b7afa8f3c04cb479906f721db8de90e8cf66f11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345191"
---
# <a name="create-a-simple-mail-item"></a>创建简单邮件项
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 可用于创建和发送请求已读回执的邮件。 当请求 "已读" 回执时, 邮件系统会生成收件人打开邮件时, 并向发件人返回阅读报告。
  
有关如何从本主题所引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目中下载、查看和运行代码的信息, 请参阅[Install the 本节中使用的示例](how-to-install-the-samples-used-in-this-section.md)。


### <a name="to-create-and-send-a-message-requesting-a-read-receipt"></a>创建和发送请求已读回执的邮件

1. 创建传出邮件。 有关如何创建传出邮件的信息, 请参阅[处理传出邮件](handling-an-outgoing-message.md)。
    
2. 添加**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性并将其设置为**true**。
    
3. 添加**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性。
    
4. 添加**PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性。
    
5. 通过调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件。 
    
CreateOutlookItemsAddin `AddMail`项目的邮件 .cpp 源文件中的函数演示这些步骤。 `AddMail`函数采用 "**添加邮件**" 对话框中的参数, 当您单击 MFCMAPI 示例应用程序中的 " **Addins** " 菜单上的 "**添加邮件**" 命令时, 将显示该对话框。 在`DisplayAddMailDialog`邮件中, cpp 中的函数显示对话框, 并将对话框中的值传递给`AddMail`函数。 该`DisplayAddMailDialog`函数与使用 MAPI 创建邮件项目不直接相关, 因此此处未列出它。 `AddMail`函数如下所示。 
  
请注意, __ 传递给该`AddMail`方法的 lpFolder 参数是一个指向[IMAPIFolder](imapifolderimapicontainer.md)接口的指针, 该接口表示将在其中创建新邮件的文件夹。 给定表示**IMAPIFolder**接口的_lpFolder_参数, 该代码调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法。 **CreateMessage**方法返回一个成功代码和一个指向[IMessage: IMAPIProp](imessageimapiprop.md)接口的指针的指针。 

大部分`AddMail`函数代码处理设置属性的工作, 以便为调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法做准备。 如果对**SetProps**方法的调用成功, 则对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用将更改提交到存储, 并创建一个新的邮件项目。 然后, 如果请求, 则调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件。 
  
`AddMail`函数使用两个 helper 函数来生成**PR_CONVERSATION_INDEX**和**PR_REPORT_TAG**属性的值: `BuildConversationIndex`和`AddReportTag`函数。 `BuildConversationIndex`函数 (位于 CreateOutlookItemsAddin 中) 执行内置 MAPI [ScCreateConversationIndex](sccreateconversationindex.md)函数在不向其传递父会话索引时所执行的操作。 在[PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)中记录了这些函数生成的会话索引缓冲区的格式。 

位于`AddReportTag` "PR_REPORT_TAG" 中的函数又调用`BuildReportTag`函数来生成**** 属性的结构。 有关`BuildReportTag`函数生成的结构的信息, 请参阅[PidTagReportTag 规范属性](pidtagreporttag-canonical-property.md)。
  
下面是该`AddMail`函数的完整列表。 
  
```cpp
HRESULT AddMail(LPMAPISESSION lpMAPISession,
            LPMAPIFOLDER lpFolder,
            LPWSTR szSubject, // PR_SUBJECT_W, PR_CONVERSATION_TOPIC
            LPWSTR szBody, // PR_BODY_W
            LPWSTR szRecipientName, // Recipient table
            BOOL bHighImportance, // PR_IMPORTANCE
            BOOL bReadReceipt, // PR_READ_RECEIPT_REQUESTED
            BOOL bSubmit,
            BOOL bDeleteAfterSubmit)
{
   if (!lpFolder) return MAPI_E_INVALID_PARAMETER;
   HRESULT hRes = S_OK;
   LPMESSAGE lpMessage = 0;
   // Create a message and set its properties
   hRes = lpFolder->CreateMessage(0,
      0,
      &lpMessage);
   if (SUCCEEDED(hRes))
   {
      // Because the properties to be set are known in advance, 
      // most of the structures involved can be statically declared 
      // to minimize expensive MAPIAllocateBuffer calls.
      SPropValue spvProps[NUM_PROPS] = {0};
      spvProps[p_PR_MESSAGE_CLASS_W].ulPropTag          = PR_MESSAGE_CLASS_W;
      spvProps[p_PR_ICON_INDEX].ulPropTag                 = PR_ICON_INDEX;
      spvProps[p_PR_SUBJECT_W].ulPropTag                = PR_SUBJECT_W;
      spvProps[p_PR_CONVERSATION_TOPIC_W].ulPropTag     = PR_CONVERSATION_TOPIC_W;
      spvProps[p_PR_BODY_W].ulPropTag                   = PR_BODY_W;
      spvProps[p_PR_IMPORTANCE].ulPropTag               = PR_IMPORTANCE;
      spvProps[p_PR_READ_RECEIPT_REQUESTED].ulPropTag   = PR_READ_RECEIPT_REQUESTED;
      spvProps[p_PR_MESSAGE_FLAGS].ulPropTag             = PR_MESSAGE_FLAGS;
      spvProps[p_PR_MSG_EDITOR_FORMAT].ulPropTag         = PR_MSG_EDITOR_FORMAT;
      spvProps[p_PR_MESSAGE_LOCALE_ID].ulPropTag         = PR_MESSAGE_LOCALE_ID;
      spvProps[p_PR_INETMAIL_OVERRIDE_FORMAT].ulPropTag = PR_INETMAIL_OVERRIDE_FORMAT;
      spvProps[p_PR_DELETE_AFTER_SUBMIT].ulPropTag      = PR_DELETE_AFTER_SUBMIT;
      spvProps[p_PR_INTERNET_CPID].ulPropTag            = PR_INTERNET_CPID;
      spvProps[p_PR_CONVERSATION_INDEX].ulPropTag         = PR_CONVERSATION_INDEX;
      spvProps[p_PR_MESSAGE_CLASS_W].Value.lpszW = L"IPM.Note";
      spvProps[p_PR_ICON_INDEX].Value.l = 0x103; // Unsent Mail
      spvProps[p_PR_SUBJECT_W].Value.lpszW = szSubject;
      spvProps[p_PR_CONVERSATION_TOPIC_W].Value.lpszW = szSubject;
      spvProps[p_PR_BODY_W].Value.lpszW = szBody;
      spvProps[p_PR_IMPORTANCE].Value.l = bHighImportance?IMPORTANCE_HIGH:IMPORTANCE_NORMAL;
      spvProps[p_PR_READ_RECEIPT_REQUESTED].Value.b = bReadReceipt?true:false;
      spvProps[p_PR_MESSAGE_FLAGS].Value.l = MSGFLAG_UNSENT;
      spvProps[p_PR_MSG_EDITOR_FORMAT].Value.l = EDITOR_FORMAT_PLAINTEXT;
      spvProps[p_PR_MESSAGE_LOCALE_ID].Value.l = 1033; // (en-us)
      spvProps[p_PR_INETMAIL_OVERRIDE_FORMAT].Value.l = NULL; // Mail system chooses default encoding scheme
      spvProps[p_PR_DELETE_AFTER_SUBMIT].Value.b = bDeleteAfterSubmit?true:false;
      spvProps[p_PR_INTERNET_CPID].Value.l = cpidASCII;
      hRes = BuildConversationIndex(
         &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.cb,
         &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb);
      if (SUCCEEDED(hRes))
      {
         hRes = lpMessage->SetProps(NUM_PROPS, spvProps, NULL);
         if (SUCCEEDED(hRes))
         {
            hRes = AddRecipient(lpMAPISession,
               lpMessage,
               MAPI_TO,
               szRecipientName);
            AddInLog(true,L"CallMenu: AddRecipient - returned hRes = 0x%08X\n",hRes);
            if (SUCCEEDED(hRes))
            {
               if (bReadReceipt)
               {
                  hRes = AddReportTag(lpMessage);
               }
               if (SUCCEEDED(hRes))
               {
                  hRes = lpMessage->SaveChanges(KEEP_OPEN_READWRITE);
                  if (SUCCEEDED(hRes) && bSubmit)
                  {
                     hRes = lpMessage->SubmitMessage(NULL);
                  }
               }
            }
         }
      }
      if (spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb)
         delete[] spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb;
   }
   if (lpMessage) lpMessage->Release();
   return hRes;
}
```

## <a name="see-also"></a>另请参阅

- [使用 MAPI 创建 Outlook 2007 项目](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

