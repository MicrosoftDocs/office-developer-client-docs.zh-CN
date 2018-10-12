---
title: 获取邮件项发件人的 SMTP 地址
TOCTitle: Get the SMTP address of the sender of a mail item
ms:assetid: 86e0c0aa-1696-4415-b25f-f9c1c29d88a9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184624(v=office.15)
ms:contentKeyID: 55119869
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 2346257dd2c23f09b77a72b08e17ba51f3f514d1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405551"
---
# <a name="get-the-smtp-address-of-the-sender-of-a-mail-item"></a><span data-ttu-id="8c997-102">获取邮件项发件人的 SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="8c997-102">Get the SMTP address of the sender of a mail item</span></span>

<span data-ttu-id="8c997-103">此代码示例获取邮件项发件人的简单邮件传输协议 (SMTP) 地址。</span><span class="sxs-lookup"><span data-stu-id="8c997-103">This example gets the sender’s Simple Mail Transfer Protocol (SMTP) address for a mail item.</span></span>

## <a name="example"></a><span data-ttu-id="8c997-104">示例</span><span class="sxs-lookup"><span data-stu-id="8c997-104">Example</span></span>

<span data-ttu-id="8c997-105">若要确定已接收邮件项的 SMTP 地址，请使用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的 [SenderEmailAddress](https://msdn.microsoft.com/library/bb622746\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8c997-105">To determine the SMTP address for a received mail item, use the [SenderEmailAddress](https://msdn.microsoft.com/library/bb622746\(v=office.15\)) property of the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object.</span></span> <span data-ttu-id="8c997-106">不过，如果发件人位于组织内部，**SenderEmailAddress** 不会返回 SMTP 地址。在这种情况下，必须使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象，才能返回发件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="8c997-106">However, if the sender is internal to your organization, **SenderEmailAddress** does not return an SMTP address, and you must use the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object to return the sender's SMTP address.</span></span>

<span data-ttu-id="8c997-107">在下面的代码示例中，GetSenderSMTPAddress 使用 **PropertyAccessor** 对象，获取未直接在 Outlook 对象模型中公开的值。</span><span class="sxs-lookup"><span data-stu-id="8c997-107">In the following code example,   uses the PropertyAccessor object to obtain values that are not exposed directly in the Outlook object model.</span></span> <span data-ttu-id="8c997-108">GetSenderSMTPAddress 需要使用 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="8c997-108"> takes in a MailItem.</span></span> <span data-ttu-id="8c997-109">如果已接收 [MailItem](https://msdn.microsoft.com/library/bb624136\(v=office.15\)) 的 **SenderEmailType** 属性值为"EX"，则表示邮件的发件人驻留在您组织内的 Exchange 服务器上。</span><span class="sxs-lookup"><span data-stu-id="8c997-109">If the value of the [SenderEmailType](https://msdn.microsoft.com/library/bb624136\(v=office.15\)) property of the received **MailItem** is "EX", the sender of the message resides on an Exchange server in your organization.</span></span> <span data-ttu-id="8c997-110">GetSenderSMTPAddress 使用 **MailItem** 对象的 [Sender](https://msdn.microsoft.com/library/ff184720\(v=office.15\)) 属性，获取由 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象表示的发件人。</span><span class="sxs-lookup"><span data-stu-id="8c997-110"> uses the Sender property of the MailItem object to get the sender, represented by the AddressEntry object.</span></span> <span data-ttu-id="8c997-111">如果 **AddressEntry** 对象表示一个 Exchange 用户，则该示例将调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法以返回 [AddressEntry](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="8c997-111">If the **AddressEntry** object represents an Exchange user, the example calls the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) method to return the [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object of the **AddressEntry** object.</span></span> <span data-ttu-id="8c997-112">然后，GetSenderSMTPAddress 使用 **ExchangeUser** 对象的 [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)) 属性，返回发件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="8c997-112"> then uses the PrimarySmtpAddress property of the ExchangeUser object to return the SMTP address of the sender.</span></span> <span data-ttu-id="8c997-113">如果发件人的 **AddressEntry** 对象不表示 **ExchangeUser** 对象，此代码示例使用 **PropertyAccessor** 对象的 [GetProperty(String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) 方法来返回发件人的 SMTP 地址，其中参数为 **PR\_SMTP\_ADDRESS** ([PidTagSmtpAddress](https://msdn.microsoft.com/library/cc842421\(v=office.15\)))。</span><span class="sxs-lookup"><span data-stu-id="8c997-113">If the AddressEntry object for the sender does not represent an ExchangeUser object, the GetProperty(String) method of the PropertyAccessor object is used, with PR_SMTP_ADDRESS ( PidTagSmtpAddress) as the argument, to return the sender's SMTP address.</span></span>

<span data-ttu-id="8c997-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="8c997-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="8c997-115">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="8c997-115">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="8c997-116">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="8c997-116">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private string GetSenderSMTPAddress(Outlook.MailItem mail)
{
    string PR_SMTP_ADDRESS =
        @"https://schemas.microsoft.com/mapi/proptag/0x39FE001E";
    if (mail == null)
    {
        throw new ArgumentNullException();
    }
    if (mail.SenderEmailType == "EX")
    {
        Outlook.AddressEntry sender =
            mail.Sender;
        if (sender != null)
        {
            //Now we have an AddressEntry representing the Sender
            if (sender.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeUserAddressEntry
                || sender.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeRemoteUserAddressEntry)
            {
                //Use the ExchangeUser object PrimarySMTPAddress
                Outlook.ExchangeUser exchUser =
                    sender.GetExchangeUser();
                if (exchUser != null)
                {
                    return exchUser.PrimarySmtpAddress;
                }
                else
                {
                    return null;
                }
            }
            else
            {
                return sender.PropertyAccessor.GetProperty(
                    PR_SMTP_ADDRESS) as string;
            }
        }
        else
        {
            return null;
        }
    }
    else
    {
        return mail.SenderEmailAddress;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="8c997-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c997-117">See also</span></span>

- [<span data-ttu-id="8c997-118">邮件</span><span class="sxs-lookup"><span data-stu-id="8c997-118">Mail</span></span>](mail.md)

