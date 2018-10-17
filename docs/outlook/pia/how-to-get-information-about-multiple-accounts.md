---
title: 获取多个帐户的信息
TOCTitle: Get information about multiple accounts
ms:assetid: 363f4058-3069-4ddc-b3ff-113a4dfd58c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184599(v=office.15)
ms:contentKeyID: 55119794
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 42d0d8439473e9404cb2e94ed9e7e83d59b4c95c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406685"
---
# <a name="get-information-about-multiple-accounts"></a>获取多个帐户的信息

Outlook 支持配置文件中包含一个或多个连接到 Exchange Server 的帐户。 此代码示例展示了如何获取并显示当前配置文件中每个帐户的杂项信息。

## <a name="example"></a>示例

下面的方法 EnumerateAccounts 显示当前配置文件中定义的每个帐户的帐户名、用户名和简单邮件传输协议 (SMTP) 地址。如果帐户已连接到 Exchange 服务器，EnumerateAccounts 将显示 Exchange 服务器名称和版本信息。如果帐户位于送达存储区，EnumerateAccounts 将显示帐户的默认送达存储区的名称。

大多数情况下，EnumerateAccounts 从 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象中访问此类信息，除非 **Account** 对象不包含用户名和 SMTP 地址的相关信息。 在这种情况下，EnumerateAccounts 使用 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 和 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象。 

EnumerateAccounts 使用通过 [CurrentUser](https://msdn.microsoft.com/library/ff184864\(v=office.15\)) 属性获取的 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象的 [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\)) 属性，以获取 **AddressEntry** 对象。 EnumerateAccounts 使用 **AddressEntry** 对象的 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法，以获取 **ExchangeUser** 对象。 

下面展示了使用 Account、AddressEntry 和 ExchangeUser 对象获取各种信息的算法：

- 如果 **Account** 对象包含有关用户名和 SMTP 地址的信息，请使用 **Account** 对象显示帐户名、用户名、SMTP 地址以及 Exchange 服务器名称和版本信息（如果该帐户为 Exchange 帐户）。

- 如果 **Account** 对象不包含有关用户名和 SMTP 地址的信息，请继续执行如下操作：
    
  - 如果该帐户不是 Exchange 帐户，请使用 **AddressEntry** 对象显示用户名和 SMTP 地址。
    
  - 如果该帐户是 Exchange 帐户，请继续执行如下操作：
        
    1.  使用 **Account** 对象显示帐户名、Exchange 服务器名称和 Exchange 版本信息。
        
    2.  **ExchangeUser** 对象可用于显示用户名和 SMTP 地址。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [帐户](accounts.md)

