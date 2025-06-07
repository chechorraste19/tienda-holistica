import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Carousel, CarouselItem } from "@/components/ui/carousel";

const products = {
  velas: ["/images/velas1.jpg", "/images/velas2.jpg"],
  esencias: ["/images/esencias1.jpg", "/images/esencias2.jpg"],
  saumerios: ["/images/saumerios1.jpg", "/images/saumerios2.jpg"],
  banos: ["/images/banos1.jpg", "/images/banos2.jpg"],
  figuras: ["/images/figuras1.jpg", "/images/figuras2.jpg"]
};

export default function TiendaHolistica() {
  return (
    <div className="bg-purple-50 text-purple-900 min-h-screen font-sans">
      <header className="text-center p-6 bg-purple-200 shadow-md">
        <h1 className="text-4xl font-bold">Tienda Holística Armonía</h1>
        <p className="text-lg mt-2">Conecta con tu esencia a través de nuestros productos</p>
      </header>

      <nav className="flex justify-center space-x-4 bg-purple-100 py-4">
        <a href="#inicio" className="hover:underline">Inicio</a>
        <a href="#nosotros" className="hover:underline">Nosotros</a>
        <a href="#productos" className="hover:underline">Productos</a>
        <a href="#contacto" className="hover:underline">Contacto</a>
        <a href="#redes" className="hover:underline">Redes Sociales</a>
      </nav>

      <section id="inicio" className="text-center py-12">
        <h2 className="text-3xl font-semibold mb-4">Bienvenidos a un espacio de armonía y bienestar</h2>
        <p className="max-w-xl mx-auto">Descubre productos cuidadosamente seleccionados para equilibrar tu energía y armonizar tus espacios.</p>
      </section>

      <section id="nosotros" className="bg-purple-100 py-12 px-4 text-center">
        <h2 className="text-3xl font-semibold mb-4">Sobre Nosotros</h2>
        <p className="max-w-2xl mx-auto">Somos una tienda virtual holística que cree en el poder de la naturaleza y los rituales. Cada artículo que ofrecemos está pensado para aportar bienestar físico, mental y espiritual.</p>
      </section>

      <section id="productos" className="py-12 px-4">
        <h2 className="text-3xl font-semibold text-center mb-8">Nuestros Productos</h2>
        {Object.entries(products).map(([categoria, imagenes]) => (
          <div key={categoria} className="mb-12">
            <h3 className="text-2xl font-medium capitalize mb-4 text-center">{categoria}</h3>
            <Carousel className="max-w-4xl mx-auto">
              {imagenes.map((img, idx) => (
                <CarouselItem key={idx}>
                  <Card>
                    <CardContent className="flex items-center justify-center p-4">
                      <img src={img} alt={categoria} className="rounded-2xl shadow-lg w-full h-64 object-cover" />
                    </CardContent>
                  </Card>
                </CarouselItem>
              ))}
            </Carousel>
          </div>
        ))}
      </section>

      <section id="contacto" className="bg-purple-100 py-12 px-4 text-center">
        <h2 className="text-3xl font-semibold mb-4">Contáctanos</h2>
        <p className="mb-6">Haz clic en el botón para hablar con nosotros directamente por WhatsApp</p>
        <a
          href="https://wa.me/573001112233" // Reemplaza este número por el tuyo real con código país
          target="_blank"
          rel="noopener noreferrer"
        >
          <Button className="bg-green-500 hover:bg-green-600 text-white text-lg px-6 py-3 rounded-full">
            Chatear por WhatsApp
          </Button>
        </a>
      </section>

      <section id="redes" className="py-12 px-4 text-center">
        <h2 className="text-3xl font-semibold mb-4">Síguenos en redes sociales</h2>
        <div className="flex justify-center space-x-6 text-2xl">
          <a href="#" className="hover:text-purple-500">Instagram</a>
          <a href="#" className="hover:text-purple-500">Facebook</a>
          <a href="#" className="hover:text-purple-500">TikTok</a>
        </div>
      </section>

      <footer className="bg-purple-200 text-center py-6 mt-12">
        <p>&copy; 2025 Tienda Holística Armonía. Todos los derechos reservados.</p>
      </footer>
    </div>
  );
}
