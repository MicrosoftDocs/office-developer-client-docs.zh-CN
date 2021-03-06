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
  
MAPI 可用于创建和发送请求已读回执的邮件。 请求已读回执时，邮件系统会在收件人打开邮件时生成一个已读报告，并返回给发件人的已读报告。
  
若要了解如何从本主题中引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目下载、查看和运行代码，请参阅安装本节中使用的示例[。](how-to-install-the-samples-used-in-this-section.md)


### <a name="to-create-and-send-a-message-requesting-a-read-receipt"></a>创建并发送请求已读回执的邮件

1. 创建传出邮件。 若要了解如何创建传出邮件，请参阅处理 [传出邮件](handling-an-outgoing-message.md)。
    
2. 将 **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，并设置为 **true**。
    
3. 将 **PR_CONVERSATION_INDEX (** [PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性。
    
4. 添加 PR_REPORT_TAG **(** [PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性。
    
5. 通过调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法发送邮件。 
    
`AddMail`CreateOutlookItemsAddin 项目的 Mails.cpp 源文件中的 函数演示了这些步骤。 该函数从"添加邮件"对话框中接受参数，该对话框在您单击 `AddMail` MFCMAPI 示例应用程序中 **"Addins"** 菜单上的"添加邮件"命令时显示。  Mails.cpp 中的 函数显示对话框，将对话框中的值传递给  `DisplayAddMailDialog`  `AddMail` 函数。 `DisplayAddMailDialog`该函数与使用 MAPI 创建邮件项目没有直接关系，因此未在此处列出。 函数  `AddMail` 如下所示。 
  
请注意，传递给该方法的 _lpFolder_ 参数是指向 IMAPIFolder 接口的指针，该接口表示将在其中 `AddMail` 创建新邮件的文件夹。 [](imapifolderimapicontainer.md) 在给定表示 **IMAPIFolder** 接口的 _lpFolder_ 参数后，代码将调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)方法。 **CreateMessage** 方法返回成功代码和指向 [指向 IMessage ： IMAPIProp 接口的指针的](imessageimapiprop.md)指针。 

大多数函数代码处理设置属性的工作，  `AddMail` 以准备调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。 如果 **对 SetProps** 方法的调用成功，则调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法会提交对存储所做的更改并创建新的邮件项目。 然后，如果请求，将调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法来发送邮件。 
  
该函数使用两个帮助程序函数来构建 PR_CONVERSATION_INDEX 和 PR_REPORT_TAG `AddMail` 属性的值：和 `BuildConversationIndex` `AddReportTag` 函数。 位于  `BuildConversationIndex` CreateOutlookItemsAddin.cpp 中的函数执行与未向内置 MAPI [ScCreateConversationIndex](sccreateconversationindex.md) 函数传递父对话索引时相同的工作。 这些函数生成的会话索引缓冲区的格式记录在 [PidTagConversationIndex 规范属性 中](pidtagconversationindex-canonical-property.md)。 

位于 Mails.cpp 中的 函数反过来调用 函数来为 PR_REPORT_TAG `AddReportTag` `BuildReportTag` 属性。  有关函数构建的结构  `BuildReportTag` 的信息，请参阅 [PidTagReportTag 规范属性](pidtagreporttag-canonical-property.md)。
  
以下是 函数的完整  `AddMail` 列表。 
  
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

- [使用 MAPI 创建Outlook 2007 项](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

