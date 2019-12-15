if (location.href.includes('thankyou')) {
    if ( Bizweb.checkout.subtotal_price) {
        var price = Bizweb.checkout.subtotal_price;
        var currency = Bizweb.checkout.currency;
        var orderId = Bizweb.checkout.order_id;

        window.dataLayer = window.dataLayer || [];
        function gtag(){ dataLayer.push(arguments); }
        gtag('event', 'conversion', {
            'send_to': '',
            'value': price,
            'currency': currency,
            'transaction_id': orderId
        });
    }
}


