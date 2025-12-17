using System;

#region Strategy Interface
public interface IPaymentMethod
{
    void ProcessPayment(decimal amount);
}
#endregion

#region Concrete Strategies
public class CreditCardPayment : IPaymentMethod
{
    public void ProcessPayment(decimal amount)
    {
        Console.WriteLine($"Processing credit card payment of {amount}");
    }
}

public class PayPalPayment : IPaymentMethod
{
    public void ProcessPayment(decimal amount)
    {
        Console.WriteLine($"Processing PayPal payment of {amount}");
    }
}

public class BankTransferPayment : IPaymentMethod
{
    public void ProcessPayment(decimal amount)
    {
        Console.WriteLine($"Processing bank transfer payment of {amount}");
    }
}
#endregion

#region Context
public class PaymentProcessor
{
    private readonly IPaymentMethod _paymentMethod;

    public PaymentProcessor(IPaymentMethod paymentMethod)
    {
        _paymentMethod = paymentMethod;
    }

    public void Process(decimal amount)
    {
        _paymentMethod.ProcessPayment(amount);
    }
}
#endregion

#region Program
class Program
{
    static void Main(string[] args)
    {
        PaymentProcessor creditCardProcessor =
            new PaymentProcessor(new CreditCardPayment());
        creditCardProcessor.Process(100m);

        PaymentProcessor payPalProcessor =
            new PaymentProcessor(new PayPalPayment());
        payPalProcessor.Process(200m);

        PaymentProcessor bankProcessor =
            new PaymentProcessor(new BankTransferPayment());
        bankProcessor.Process(300m);
    }
}
#endregion
