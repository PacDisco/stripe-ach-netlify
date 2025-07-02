const stripe = require('stripe')(process.env.STRIPE_SECRET_KEY); // Replace this

exports.handler = async () => {
  try {
    const intent = await stripe.paymentIntents.create({
      amount: 200000,
      currency: 'usd',
      payment_method_types: ['us_bank_account'],
    });

    return {
      statusCode: 200,
      body: JSON.stringify({ clientSecret: intent.client_secret }),
    };
  } catch (error) {
    return {
      statusCode: 500,
      body: JSON.stringify({ error: error.message }),
    };
  }
};
