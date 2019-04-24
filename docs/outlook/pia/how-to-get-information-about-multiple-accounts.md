---
title: 获取多个帐户的信息
TOCTitle: Get information about multiple accounts
ms:assetid: 363f4058-3069-4ddc-b3ff-113a4dfd58c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184599(v=office.15)
ms:contentKeyID: 55119794
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d065761b9296f1c0eb3043e9b9778e438790f94e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349411"
---
# <a name="get-information-about-multiple-accounts"></a><span data-ttu-id="e8a31-102">获取多个帐户的信息</span><span class="sxs-lookup"><span data-stu-id="e8a31-102">Get information about multiple accounts</span></span>

<span data-ttu-id="e8a31-103">Outlook 支持配置文件中包含一个或多个连接到 Exchange Server 的帐户。</span><span class="sxs-lookup"><span data-stu-id="e8a31-103">Outlook supports a profile that contains one or more accounts that are connected to an Exchange Server.</span></span> <span data-ttu-id="e8a31-104">此代码示例展示了如何获取并显示当前配置文件中每个帐户的杂项信息。</span><span class="sxs-lookup"><span data-stu-id="e8a31-104">This example shows how to obtain and display miscellaneous information about each account in the current profile.</span></span>

## <a name="example"></a><span data-ttu-id="e8a31-105">示例</span><span class="sxs-lookup"><span data-stu-id="e8a31-105">Example</span></span>

<span data-ttu-id="e8a31-p102">下面的方法 EnumerateAccounts 显示当前配置文件中定义的每个帐户的帐户名、用户名和简单邮件传输协议 (SMTP) 地址。如果帐户已连接到 Exchange 服务器，EnumerateAccounts 将显示 Exchange 服务器名称和版本信息。如果帐户位于送达存储区，EnumerateAccounts 将显示帐户的默认送达存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="e8a31-p102">The following method, EnumerateAccounts, displays the account name, user name, and Simple Mail Transfer Protocol (SMTP) address for each account that is defined in the current profile. If the account is connected to an Exchange server, EnumerateAccounts displays the Exchange server name and version information. And if the account resides on a delivery store, EnumerateAccounts displays the name of the default delivery store for the account.</span></span>

<span data-ttu-id="e8a31-109">大多数情况下，EnumerateAccounts 从 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象中访问此类信息，除非 **Account** 对象不包含用户名和 SMTP 地址的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e8a31-109">EnumerateAccounts accesses most of this information from the [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object, except when the **Account** object does not contain information about the user name and SMTP address.</span></span> <span data-ttu-id="e8a31-110">在这种情况下，EnumerateAccounts 使用 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 和 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="e8a31-110">In that case, EnumerateAccounts uses the [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) and [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) objects.</span></span> 

<span data-ttu-id="e8a31-111">EnumerateAccounts 使用通过 [CurrentUser](https://msdn.microsoft.com/library/ff184864\(v=office.15\)) 属性获取的 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象的 [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\)) 属性，以获取 **AddressEntry** 对象。</span><span class="sxs-lookup"><span data-stu-id="e8a31-111">EnumerateAccounts obtains the **AddressEntry** object by using the [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\)) property of the [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object obtained from the [CurrentUser](https://msdn.microsoft.com/library/ff184864\(v=office.15\)) property.</span></span> <span data-ttu-id="e8a31-112">EnumerateAccounts 使用 **AddressEntry** 对象的 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法，以获取 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="e8a31-112">EnumerateAccounts obtains the **ExchangeUser** object by using the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) method of the **AddressEntry** object.</span></span> 

<span data-ttu-id="e8a31-113">下面展示了使用 Account、AddressEntry 和 ExchangeUser 对象获取各种信息的算法：</span><span class="sxs-lookup"><span data-stu-id="e8a31-113">The following is the algorithm to obtain various information by using the Account, AddressEntry, and ExchangeUser objects:</span></span>

- <span data-ttu-id="e8a31-114">如果 **Account** 对象包含有关用户名和 SMTP 地址的信息，请使用 **Account** 对象显示帐户名、用户名、SMTP 地址以及 Exchange 服务器名称和版本信息（如果该帐户为 Exchange 帐户）。</span><span class="sxs-lookup"><span data-stu-id="e8a31-114">If the **Account** object contains information about the user name and SMTP address, use the **Account** object to display the account name, user name, SMTP address, and Exchange server name and version information if the account is an Exchange account.</span></span>

- <span data-ttu-id="e8a31-115">如果 **Account** 对象不包含有关用户名和 SMTP 地址的信息，请继续执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="e8a31-115">If the **Account** object does not contain information about the user name and SMTP address, proceed as follows:</span></span>
    
  - <span data-ttu-id="e8a31-116">如果该帐户不是 Exchange 帐户，请使用 **AddressEntry** 对象显示用户名和 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="e8a31-116">If the account is not an Exchange account, use the **AddressEntry** object to display the user name and SMTP address.</span></span>
    
  - <span data-ttu-id="e8a31-117">如果该帐户是 Exchange 帐户，请继续执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="e8a31-117">If the account is an Exchange account, proceed as follows:</span></span>
        
    1.  <span data-ttu-id="e8a31-118">使用 **Account** 对象显示帐户名、Exchange 服务器名称和 Exchange 版本信息。</span><span class="sxs-lookup"><span data-stu-id="e8a31-118">Use the **Account** object to display the account name, Exchange server name, and Exchange version information.</span></span>
        
    2.  <span data-ttu-id="e8a31-119">**ExchangeUser** 对象可用于显示用户名和 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="e8a31-119">Use the **ExchangeUser** object to display the user name and SMTP address.</span></span>

<span data-ttu-id="e8a31-120">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="e8a31-120">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="e8a31-121">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="e8a31-121">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="e8a31-122">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="e8a31-122">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void EnumerateAccounts()
{
    Outlook.Accounts accounts =
        Application.Session.Accounts;
    foreach (Outlook.Account account in accounts)
    {
        try
        {
            StringBuilder sb = new StringBuilder();
            sb.AppendLine("Account: " + account.DisplayName);
            if (string.IsNullOrEmpty(account.SmtpAddress)
                || string.IsNullOrEmpty(account.UserName))
            {
                Outlook.AddressEntry oAE =
                    account.CurrentUser.AddressEntry
                    as Outlook.AddressEntry;
                if (oAE.Type == "EX")
                {
                    Outlook.ExchangeUser oEU =
                        oAE.GetExchangeUser()
                        as Outlook.ExchangeUser;
                    sb.AppendLine("UserName: " +
                        oEU.Name);
                    sb.AppendLine("SMTP: " +
                        oEU.PrimarySmtpAddress);
                    sb.AppendLine("Exchange Server: " +
                        account.ExchangeMailboxServerName);
                    sb.AppendLine("Exchange Server Version: " +
                        account.ExchangeMailboxServerVersion); 
                }
                else
                {
                    sb.AppendLine("UserName: " +
                        oAE.Name);
                    sb.AppendLine("SMTP: " +
                        oAE.Address);
                }
            }
            else
            {
                sb.AppendLine("UserName: " +
                    account.UserName);
                sb.AppendLine("SMTP: " +
                    account.SmtpAddress);
                if(account.AccountType == 
                    Outlook.OlAccountType.olExchange)
                {
                    sb.AppendLine("Exchange Server: " +
                        account.ExchangeMailboxServerName);
                    sb.AppendLine("Exchange Server Version: " +
                        account.ExchangeMailboxServerVersion); 
                }
            }
            if(account.DeliveryStore !=null)
            {
                sb.AppendLine("Delivery Store: " +
                    account.DeliveryStore.DisplayName);
            }
            sb.AppendLine("---------------------------------");
            Debug.Write(sb.ToString());
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e8a31-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8a31-123">See also</span></span>

- [<span data-ttu-id="e8a31-124">帐户</span><span class="sxs-lookup"><span data-stu-id="e8a31-124">Accounts</span></span>](accounts.md)

