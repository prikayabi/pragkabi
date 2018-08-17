# prakabi
from meya import Component
class foodConfirmation(Component):
	def start(self):
	       # read the order and make lower case
	        order = self.db.flow.get('food type') or ""
	        order = order.lower()
	        print order
          print(" vegitarien hotel");
	       # conditional
	         if "chiken" in order:
	            text = "sorry.. nonveg is not available"
	         elif "cake" in order:
	            text = "sorry..bakery items not available "
           elif "hgweuh" in order:
              text = "please..type the correct spelling"
	         elif order:
	            text = "Thanks for your order!: {}".format(order)
	         else:
	            text = "No order received :("
          # respond to the user
	          message = self.create_message(text=text)
	          return self.respond(message=message, action="next")
